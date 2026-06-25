# Voice Analysis (calibrate from the student's real writing)

Run this when the student gives you past writing samples. It is optional, but it is the single biggest lever for matching their voice. Rules and a short sample get you close. Real samples give you their actual fingerprint.

## What to ask for
Ask for 1 to 4 pieces the student actually wrote. Past graded essays are best, because they show the student's formal register, which is what coursework needs. Application essays, memos, or long thoughtful emails also work. More is better, but even one helps. They can paste the text or drop the files.

## What to extract (the voice fingerprint)
Read every sample and pull out each of these, with a short verbatim quote as evidence:

1. **Rhythm.** Typical sentence length, and how much it varies. Do they mix short punches with long lines, or run uniform? How often do they use fragments? Paragraph length.
2. **Diction.** Formal or casual register. Vocabulary level. Contractions or not. Words and phrases they reach for. Words they avoid.
3. **Stance.** How opinionated. How much they hedge. First person or not. How they address the reader.
4. **Structure.** How they open a piece (cold, thesis-first, anecdote, question). How they build an argument. How they close. How often they use lists.
5. **Mechanics.** Comma habits, parentheses, semicolons, dashes, any capitalization quirks.
6. **Tells to keep.** The two or three moves that make the writing unmistakably theirs.
7. **Anti-patterns.** Things they never do, so the AI does not add them.

Watch one trap: a person's casual writing (fast chat, lowercase, typos) is not their formal writing. If the samples are casual, infer the formal register they would use for a graded paper, and say you did that. Keep the real character. Do not flatten it into a generic "academic" voice.

## What to write
Write the result into the **Voice fingerprint** section of `profile.md` as a compact spec covering the seven points above, plus 2 to 4 short verbatim excerpts as exemplars the section agents can imitate. Set the section status to calibrated and date it. Keep the raw samples in a `voice-samples/` folder inside the skill so you can re-analyze later. When the student adds more samples, re-run this and update the fingerprint.

## How the rest of the skill uses it
- **Section agents** read the voice fingerprint and the exemplars before drafting, and imitate that specific rhythm and diction, not a generic target.
- **The reviewer** checks the draft against the fingerprint, not only the generic anti-slop list. A draft can be slop-free and still miss the student's actual voice. The fingerprint is what catches that.
