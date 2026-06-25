---
owner: "[your name]"
confirmed: false
---

# Student Profile: [Your name]

> `confirmed: false` means this profile is still a blank template you haven't filled in.
> On the first run, the skill walks you through filling it, then sets `confirmed: true`.
> Replace every `[bracketed placeholder]` with your own details. Delete the examples.
>
> The two inputs that matter most are your **writing samples** and your **writing rules** below. Personal background is optional, fill it only if you want.

## How you write (voice rules, enforce in every sentence)
These are sensible defaults that produce sharp, human writing. Keep the ones that fit you and edit or delete the rest. They are yours to change.

- **No em dashes.** Use commas, periods, parentheses, colons, or line breaks instead.
- **Plain words.** Use the simple word. "use" not "leverage", "first customers" not "beachhead", "grows" not "compounds". If a word sounds like a consulting deck or a LinkedIn post, cut it.
- **Vary the rhythm. This is the big one.** Real writing has burstiness: a short punchy line next to a longer one, and the occasional fragment. AI writing is a wall of medium-length, perfectly balanced sentences. Break that pattern on purpose. A three-word sentence is allowed. So is a fragment.
- **Use contractions.** "it's" not "it is", "that's" not "that is", "don't" not "do not", "can't" not "cannot". Even in a formal academic register, contractions read more human. Writing that never contracts is a quiet AI tell.
- **Flow first, then grammar.** A sentence has to make sense, but first it has to read smoothly out loud. If two clipped sentences flow better joined with "but" / "and" / "so", join them.
- **Say it once and move on.** No signposting ("The key insight is", "What this proves"). No throat-clearing intros. No warm closers.
- **Direct and opinionated.** Take the position, back it, move. Sharp and a little blunt beats balanced and bland.
- **Concrete over abstract.** Real examples, real numbers, real companies, preferably from worlds you know.
- **[Add your own hard rules here.]** Anything about how you write that the defaults miss. Words you always avoid, a register you prefer, a citation style, a reading level to target.

## Your writing samples (the most important input)
Paste a few lines of your own real writing here so the tool matches your actual voice, not a generic one. A graded essay, a memo, a long thoughtful email, anything you actually wrote. The closer to the register you need for coursework, the better.

> [Paste 2 to 6 lines of your own writing here.]

For a much closer match, drop in 1 to 4 full samples and the skill analyzes them into a voice fingerprint below (see [references/voice-analysis.md](references/voice-analysis.md)).

## Voice fingerprint (from real writing samples)
Status: not calibrated yet. This stays empty until you give the skill real writing samples.

When you provide samples, the skill runs [references/voice-analysis.md](references/voice-analysis.md) and fills this with a compact spec of your rhythm, diction, stance, structure, and mechanics, plus a few short verbatim excerpts the section agents imitate. Until then, the voice rules above are what's used.

## Banned AI-slop (the reviewer FAILS the draft on these, no matter how good the content is)
The full, growing catalog lives in [references/ai-slop.md](references/ai-slop.md), and a dedicated slop-checker scans every draft against it. The worst offenders:
- **Buzzwords:** beachhead, leverage, unlock, robust, seamless, harness, empower, elevate, supercharge, game-changer, cutting-edge, holistic, synergy, paradigm, tapestry, "deep dive", "the power of", "at the end of the day", "in today's world", "plays a crucial/pivotal role", "it is worth noting".
- **The colon-elaboration tic:** opening a sentence with "Noun: explanation" ("The core problem: ..."). Rewrite as a normal sentence.
- **The antithesis tic:** "It is not X. It is Y." Allowed once per document at most.
- **Rule-of-three everywhere:** "risky, generic, and mediocre." Sometimes two, sometimes one.
- **Hype adjectives as filler:** remarkably, powerful, compelling, significant, standout.
- **Severed-list fragments and chopped clauses:** a list dropped as a fragment, or flat clauses chopped apart where one flowing line reads better.

## Program context (the practical basics)
Fill these so the quality loop knows how hard to push and what format to hit:
- **Program and courses:** [your program, its length, and courses or professors as you learn them]
- **Target grade / standard:** [e.g. "aim for top of class" vs "solid pass". Sets how hard the quality loop pushes.]
- **Citation style:** [APA, MLA, Chicago, or none]
- **Deliverable norms:** [group vs individual, length expectations, language]

## Optional: who you are (background and lens)
Optional. Skip this whole section if you'd rather. Filling it in gives the writing a point of view on open-ended prompts (ideate, analyze, recommend), but your samples and rules above already carry your voice.

- **Background:** [If you want: your field, what you do or did, what you know well. Becomes your "lens" so open-ended answers reach for your world, not the textbook's.]
- **How you think:** [If you want: how you approach a problem. Practical operator, theoretical, creative, data-driven, founder-minded.]
- **What you reach for:** [If you want: examples, industries, or markets that come naturally to you, and what you're skeptical of.]

## Notes
- This profile is the portable, self-contained memory of the skill. It needs no external app to run. Fill it in once, edit it any time, and every run reads from it.
