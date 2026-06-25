# Brainstorm Phase (creative assignments only, gated)

Some assignments have no "correct" deliverable to execute. They ask the student to invent something: an idea, a product, a campaign, a concept, a pitch. For those, writing well is not enough. If the underlying idea is the obvious one, the work is generic no matter how good the prose. This phase makes the idea original, interesting, and genuinely the student's, before any drafting starts.

It is interactive. It starts by asking the student what they think, brainstorms with them, and does not move on until the student has an idea they actually want to build.

## When to run it (the gate, all three must hold)
Run this phase only if ALL of these are true:
1. **The assignment needs creativity.** It asks the student to ideate, propose, design, invent, pitch, or create something original, with no single prescribed answer. Skip it for fixed-form work: analyze this case, compare X and Y, write an essay on a set topic, solve this problem, summarize, reflect.
2. **The student has not already given a solution.** If they already said "I want to do X" or dropped in their idea, skip the divergence. Run one quick originality check on their idea instead, then draft.
3. **The student's context does not already point to a clear idea.** If the assignment obviously maps to something they are already building or have a strong stated interest in (check profile.md), surface that as the default and confirm it, rather than forcing a blank-page brainstorm.

If any one of these is false, skip this phase and go to Phase 2. Do not force a brainstorm on someone who already knows what they want, or on an assignment with a fixed answer. (Worked example: a project where the student says "use the skill itself as my idea" fails condition 2, so this phase does not run.)

## How to run it (orchestrator, interactive with the student)

### Step 1: Ask first, do not pitch first
Open by asking the student for their raw input. For example: "Before I suggest anything, what is your gut here? Any half-formed idea, any angle that interests you, anything you definitely do not want to do?" Capture it. Their seed is the most likely source of something original, and it tells you what they actually have energy for.

### Step 2: Name the obvious answer, then avoid it
Say the modal answer out loud. "The obvious version of this is X. Half the class will hand in a version of X." Then steer away from it, unless the student wants it. The whole point is to not be the modal answer.

### Step 3: Diverge (spawn the divergent-ideas sub-agent)
Spawn a sub-agent to generate 4 to 6 genuinely different directions, grounded in the student's profile and lens (profile.md), deliberately avoiding the obvious answer. Brief it to use moves like:
- Set the idea in a world the student actually knows (their industry, their past work).
- Combine two unrelated domains the student cares about.
- Invert the problem. What if the opposite were the goal?
- Take the contrarian position the room would not.
- Find the narrowest, sharpest version instead of the broad safe one.
Return them as short punchy options, each with its hook (why it is interesting) and its risk.

### Step 4: Brainstorm with the student (the actual back-and-forth)
Put the options in front of the student in plain language. Push. Which one makes them lean in? Which one could they not stop thinking about? Which one would they be a little nervous to present? (Nervous is often a sign it is interesting.) React to their answers, combine options, throw out the dead ones. This is a conversation, not a menu. Keep going until one idea has real energy behind it.

### Step 5: Pressure-test for originality (spawn the originality red-team sub-agent)
Once an idea leads, stress-test it. Spawn a sub-agent (or check directly) on three questions:
- Would 20 other students land on roughly this? If yes, it is not original yet. Sharpen it.
- What is the strongest objection a smart professor would raise? Can the idea survive it?
- Is the student actually excited to build this, or just settling? If settling, go back to Step 4.

### Step 6: Converge and confirm
Land on ONE idea. State it back in two or three sentences: what it is, why it is interesting, why it is the student's and not generic. Get an explicit yes. Then write a short **creative brief** (the idea, the angle, the hook, what makes it original, any constraints the student set) and hand it to Phase 2 and the drafting pipeline. Everything downstream builds on this brief.

## Output
A confirmed creative brief: the chosen idea, its hook, why it is original, and the student's stated constraints. The section agents in Phase 3 treat this brief as the spine of the deliverable.

## Principle
This is the anti-generic rule applied to ideas, the same way the slop catalog applies it to prose. Good writing around a modal idea is still a modal submission. Originality starts at the concept, and the student has to actually want it.
