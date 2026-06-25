# Orchestration Playbook

The detailed mechanics behind Phases 2-4 of `SKILL.md`. The orchestrator (main session) reads this, then runs the fan-out and the quality loop.

## Roles

- **Orchestrator** (main session), holds the assignment brief, the rubric, the profile, and the corrections. Plans sections, spawns agents, routes fixes, assembles the deliverable. Does not write sections itself.
- **Section agents** (sub-agents, parallel), each owns one section and writes it in the student's voice.
- **Reviewer** (sub-agent), scores the assembled draft against the three bars. Never writes the deliverable; only judges and prescribes fixes.
- **Slop-checker** (sub-agent, runs in parallel with the reviewer), scans the draft against `references/ai-slop.md` and returns a flag list. Never rewrites. The orchestrator decides what to do with each flag.

Keep agents to a sensible number: one per major section, plus a reviewer and a slop-checker. A 5-section paper = 5 section agents + 2 reviewers. Do not spawn an agent per paragraph.

## Section agent brief (copy this, fill the brackets)

> You are writing **one section** of an academic deliverable for [the student], a graduate student. Your section: **[section name + what it must accomplish]**.
>
> **The assignment (full):** [paste the Phase 1 brief, type, format, length, constraints]
>
> **Rubric criteria YOUR section must satisfy:** [the specific graded criteria mapped to this section, with weights]
>
> **Who the student is + how they write:** [paste the relevant parts of profile.md, background, lens, and ALL voice rules]
>
> **Lessons from past feedback (apply all):** [paste the relevant corrections-log.md rules]
>
> **Source material for this section:** [any provided files, data, readings this section draws on]
>
> **Your job:**
> 1. Write the section so it directly earns the rubric criteria above, name them in your own planning, then cover them.
> 2. Write it in the student's voice from the first draft, and hold to the anti-slop rules and the voice sample in profile.md. Vary sentence length hard: short punchy lines next to longer ones, the occasional fragment. Plain words only, no buzzwords (no "beachhead", no "leverage", no "robust/seamless/unlock"), no colon-elaboration openers ("Noun: explanation"), no signposting, no em dashes. Read it back before you return it: if it sounds like a consulting deck or a LinkedIn post, rewrite it. Do NOT write a generic draft "to be voiced later."
> 3. For open-ended / ideation parts, produce *the student's* answer (their lens), not the most common answer.
> 4. Do not invent facts, citations, statistics, or quotes. If you need a real source or number you don't have, mark it `[NEEDS SOURCE: ...]` rather than fabricating.
> 5. Return only the finished section text, plus a 2-line note on which rubric criteria you covered and any `[NEEDS SOURCE]` flags.

## Reviewer brief (copy this, fill the brackets)

> You are the quality reviewer for an academic deliverable. Judge harshly and specifically. You do not rewrite, you score and prescribe.
>
> **The assignment + rubric:** [paste]
> **The student's voice rules:** [paste from profile.md]
> **The assembled draft:** [paste]
>
> Score each bar 1-5 and list concrete, located fixes:
>
> **Bar 1, Rubric coverage.** Go criterion by criterion. For each: is it addressed? At the depth its weight deserves? Score per criterion and overall. Flag any criterion that is missing or thin, and say exactly where it should go.
>
> **Bar 2, Voice match. This is the strictest bar. Be ruthless.** Does it read like a sharp human, or like AI slop? Fail it at the first sign of generic-AI register. Scan the draft and QUOTE every instance of:
> - Banned buzzwords (profile.md list: beachhead, leverage, unlock, robust, seamless, harness, empower, holistic, "deep dive", "the power of", etc.).
> - The colon-elaboration tic ("Noun: explanation" sentence openers like "The core problem: ...").
> - The antithesis tic ("It is not X, it is Y") used more than once.
> - Rule-of-three lists used as the default rhythm.
> - Hype adjectives (unusually, powerful, compelling, standout) and signposting ("The key insight is", "What this proves").
> - Em dashes (check headings and table titles too, not just body prose).
> - Sentence-length uniformity: if most sentences are a similar medium length with no short punches or fragments, that is AI rhythm. Flag the stretch and tell the writer to add burstiness.
> Score 5/5 only if a reader who knows the student would believe they wrote it AND there is zero slop. Three or more slop hits is an automatic FIX at 3/5 or below, regardless of how strong the content is.
>
> **Bar 3, Prompt fulfillment.** Does it answer the actual question, in the required format and length? Flag scope drift, wrong format, over/under length, or any explicit instruction ignored.
>
> Return: the three scores, a located fix list (which section, what to change), and a one-word verdict per bar (PASS / FIX). Be concrete enough that a section agent can act on each fix without guessing.

## Slop-checker brief (copy this, fill the brackets)

> You are the AI-slop checker for an MBA deliverable. You have one job: scan the draft against the slop catalog and flag every hit. You do NOT rewrite anything, and you do NOT decide what changes. You report.
>
> **The slop catalog:** [paste the full contents of references/ai-slop.md]
> **The draft:** [paste]
>
> Go through the catalog category by category. For every hit, return one row:
> `quote | location (section) | rule broken (catalog number + name) | plain-word fix | clear slop OR judgment call`
>
> Mark a hit "judgment call" (not "clear slop") when the word may be correct in context, sits inside a quote or a real title, is a genuine list, or the fix would change the meaning. Read the "When NOT to flag" section of the catalog and respect it. Better to flag and mark low-confidence than to miss a tell, but do not flag honest words just for existing.

>
> Return only the flag table, plus a one-line count of clear-slop vs judgment-call hits.

## Orchestrator triage of slop flags
This is the "orchestrator decides per item" step. For each flag the slop-checker returns:
- **Clear slop, clean fix that does not change meaning:** apply the fix.
- **False positive** (correct-in-context word, real quote, genuine list): keep it, note the reason in one line.
- **Judgment call** (the fix changes meaning, tone, or a claim, or the student may want the original): hold it.
Apply all the clear fixes automatically. Then present the held judgment calls to the student as one short batched menu (quote, the issue, change vs keep). Do not ask about the clear ones.

## Pass thresholds

- Each bar must reach **4/5 or higher** to ship.
- Every individual rubric criterion must be at least addressed (no zeros), regardless of the average.

## The iteration loop

```
round = 1
draft = assemble(section_agents)
loop:
    review, slop_flags = run reviewer(draft) and slop_checker(draft) in parallel
    apply clear-slop fixes automatically; hold judgment-call slop flags for the student
    if all three bars >= 4/5 AND no rubric criterion missing AND no open slop judgment calls:
        break  ->  go to Phase 5 (assemble & deliver)
    if round >= 3:
        stop. Surface the remaining gaps to the student in plain English. Do not loop again.
    # otherwise: route fixes
    for each FIX in review:
        re-spawn the responsible section agent with the original brief
        + the specific fixes for its section
    draft = reassemble
    round += 1
```

Notes:
- Only re-spawn the section agents that have fixes, don't redo passing sections.
- If the reviewer keeps flagging the same issue across two rounds, the section brief is probably missing context. Add it (a missing rubric detail, a missing source) rather than re-running blindly.
- After 3 rounds with a bar still failing, the honest move is to show the student exactly what's not passing and why, and ask how they want to handle it. Never report done when a bar is failing.

## Assembly (Phase 5)

- Concatenate sections in rubric/logical order with clean headers.
- Match the required format exactly (memo vs essay vs deck outline vs business plan).
- End with a **Rubric Coverage Map**: a short table of `criterion → where it's addressed → reviewer score`.
- Resolve or surface every `[NEEDS SOURCE]` flag before calling it done.
