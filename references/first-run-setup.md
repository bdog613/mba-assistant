# First-Run Setup

Run this **only** when `profile.md` is missing, empty, or `confirmed: false`. Goal: end with a `profile.md` the student has verified, marked `confirmed: true`. After that, the skill never runs this again unless asked.

The template ships with a blank `profile.md` (all `[bracketed placeholders]`, `confirmed: false`). So on a fresh install you'll almost always be in Case B, the short interview. Case A is for when a profile already has real content but hasn't been confirmed yet.

## Case B: a blank or new profile (the normal first run)

Build the profile via a short interview. Ask these, batched into one message, not one question at a time:
1. Name, university/program, and how long the program is.
2. Background, what they did before, what they know well (this becomes their "lens" for non-generic answers).
3. How they think about problems (academic/theoretical, practical/operator, creative, data-driven, etc.).
4. Writing voice, formal or conversational, any hard rules (e.g. no em dashes), reading level to target.
5. A writing sample, paste 1-2 paragraphs they've written, so the voice can be matched, not guessed.
6. Program specifics, grade target, citation style, group vs individual norms, language.

Then write `profile.md` filling every placeholder with their answers, set `confirmed: true`, and continue.

Keep it to one round-trip if you can. Don't block the actual work on perfect profile completeness, anything still unknown can be filled the first time it matters.

## Case A: profile.md exists but is `confirmed: false`

The profile already has real content (the student filled some of it in, or carried it over) but hasn't been verified. Do this:
1. Show them the profile in the chat, readably (not as a file path).
2. Point at any line that's still a placeholder or marked **(confirm)** and ask them to fill or correct those, batched into one short message.
3. Ask the two highest-value open questions if still unknown:
   - "What grade standard are we aiming for, top of class, or a solid pass?" (sets how hard the quality loop pushes)
   - "What citation style does the program expect, if any?"
4. Apply their answers, resolve the placeholders, set `confirmed: true`, and continue to the assignment.

## Voice calibration from real writing (optional, highest-value step)
The voice rules in profile.md get the writing close. Real samples get it right. At setup, and any time later, offer this:

> Optional: paste or drop in 1 to 4 things you have written (past graded essays work best for coursework, but memos or long emails are fine). I will analyze how you actually write and store it, so future work matches your real voice instead of a generic one. Skip it and I will use the voice rules instead.

If the student provides samples, run [voice-analysis.md](voice-analysis.md) and fill the Voice fingerprint section of profile.md. If they skip, continue with the rules. Never block the work on this.

## Importing context from a prior chat

The skill cannot read claude.ai web chat history directly. If the student wants to carry over context from an earlier conversation, have them paste the relevant part; fold the stable facts and preferences into `profile.md` (not the one-off details), confirm, and continue.
