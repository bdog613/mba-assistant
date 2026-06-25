# Brainstorm Phase (creative or open-subject assignments, gated)

Some assignments don't hand you a deliverable to execute. They ask you to invent or choose something: an idea, a product, a campaign, a concept, a pitch, or a subject to work on (a company, a market, a case). For those, the system leads. It does the research and the thinking, puts concrete options in front of the student, and ideates with them to land on one that's original and genuinely theirs. The student chooses and steers, they never start from a blank page.

## When to run it (the gate, all three must hold)
Run this phase only if ALL of these are true:
1. **The assignment needs a choice or an invention.** It asks the student to ideate, propose, design, pitch, or create something original, OR to pick a subject the assignment then works on (analyze a company, choose a market, select a case). Skip it for fully fixed work: analyze this specific case, compare X and Y, write an essay on a set topic, solve this problem.
2. **The student has not already given a solution.** If they already said "I want to do X" or dropped in their idea or subject, skip the divergence. Run one quick originality check on their choice instead, then proceed.
3. **The student's context does not already point to a clear choice.** If the assignment obviously maps to something they're already building or have a strong stated interest in (check profile.md), surface that as the default and confirm it.

If any one is false, skip to Phase 2. (Worked example: a project where the student says "use the skill itself as my idea" fails condition 2, so this phase does not run.)

## How to run it (orchestrator: propose first, then ideate with the student)

### Step 1: Do the legwork and generate concrete options
Do NOT open by asking "what's your idea?" or "which company do you want?" That offloads the research and thinking to the student, which is the opposite of the point. Generate the options yourself first:
- Spawn a **divergent-ideas sub-agent** to produce 4 to 6 genuinely different directions, grounded in the student's profile and lens (profile.md), deliberately avoiding the obvious answer.
- If the assignment needs a **subject the student must pick** (a company, a market, a case, a product), research concrete, real candidates that fit this specific assignment and rubric. Don't ask the student to name one.

Each option comes with its hook (why it's interesting, or why it fits the assignment) and its catch (the risk or the hard part).

Divergence moves for the sub-agent:
- Set the idea in a world the student actually knows (their industry, their past work).
- Combine two unrelated domains they care about.
- Invert the problem. What if the opposite were the goal?
- Take the contrarian position the room wouldn't.
- Find the narrowest, sharpest version instead of the broad safe one.

For subject-selection, bias toward concrete, real, well-documented choices the student can actually research and write about, each with a one-line reason it fits.

### Step 2: Lead with the options, name the obvious answer, and steer
Put the 4 to 6 options in front of the student in plain language, as a real menu. Say the obvious answer out loud ("half the class will do a version of X") and steer away from it unless they want it. Always include a "or tell me your own and I'll run with it" path. The student is reacting to concrete, researched choices, not generating from scratch.

### Step 3: Ideate with the student (the back-and-forth)
Now work with them. Which option do they lean into? Which could they not stop thinking about? Which would they be a little nervous to present? (Nervous is often a sign it's interesting.) React, combine options, sharpen, throw out the dead ones. This is the collaborative part, a conversation, not a one-shot menu. Keep going until one choice has real energy.

### Step 4: Pressure-test for originality (spawn the originality red-team sub-agent)
Once one leads, stress-test it:
- Would 20 other students land on roughly this? If yes, sharpen it.
- What's the strongest objection a smart professor would raise? Can it survive?
- Is the student actually excited about this, or just settling? If settling, go back to Step 3 with the other options.

### Step 5: Converge and confirm
Land on ONE choice. State it back in two or three sentences: what it is, why it's interesting or why it fits, why it's the student's and not generic. Get an explicit yes. Then write a short **creative brief** (the idea or subject, the angle, the hook, what makes it original or well-fitted, any constraints the student set) and hand it to Phase 2 and the drafting pipeline.

## Output
A confirmed creative brief: the chosen idea or subject, its hook, why it works, and the student's stated constraints. The section agents in Phase 3 treat this brief as the spine of the deliverable.

## Principle
The system carries the work, so it leads with concrete, researched options instead of open-ended questions. The student decides and steers, they never have to go research or brainstorm on their own before the system has done its part. Originality starts at the concept, and the student has to actually want it.
