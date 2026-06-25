# AI Slop Catalog

The slop-checker reviewer reads this file and scans every draft against it. Each hit gets flagged with a quote and the rule it breaks. The orchestrator then decides per flag: fix it, keep it (with a reason), or ask the student. Nothing here is auto-deleted. A flag is a question, not a verdict.

This file is meant to grow, and it learns from feedback. Whenever the student reacts to a draft with "this sounds AI-written", "too generic", or "make it more human", find the exact lines that triggered it, add those patterns here as new entries, and fix the draft. Next time, the slop-checker catches them on its own.

## How to use this (slop-checker reviewer)
Scan the draft against every category below. For each hit, record: the exact quote, where it is, which rule it breaks, a plain-word fix, and whether it is clear slop or a judgment call. Do not rewrite the draft. Return a flag list.

## How to use this (orchestrator)
Triage each flag, one at a time:
- **Clear slop, clean fix that does not change meaning:** fix it.
- **False positive** (correct-in-context word, real quote, genuine list): keep it, note why in one line.
- **Judgment call** (the fix changes meaning, tone, or a claim, or the student may want the original): hold it for the student.
Apply all the clear fixes, then present the held judgment calls to the student as one short batched menu. Do not ask about the clear ones.

---

## 1. Buzzwords and corporate-speak
Replace with the plain word.
beachhead, wedge (as jargon), leverage (as a verb), unlock, harness, empower, elevate, supercharge, streamline, robust, seamless, scalable (as filler), turnkey, best-in-class, world-class, cutting-edge, state-of-the-art, next-generation, game-changer, disruptive, synergy, holistic, paradigm, ecosystem (figurative), landscape (figurative), realm, "the X space", vertical (as jargon).

## 2. The "delve" family (essay-AI tells)
These scream language model.
delve, tapestry, testament (to), underscore, showcase, boast, navigate (figurative), foster, garner, myriad, plethora, pivotal, crucial, vital, profound, intricate, nuanced, multifaceted, comprehensive.

## 3. Empty openers and filler phrases
Cut them, or replace with the short version.
"In today's fast-paced world", "In the ever-evolving landscape of", "In an age where", "Now more than ever", "When it comes to", "In order to" (use "to"), "due to the fact that" (use "because"), "it is worth noting that", "it is important to note that", "needless to say", "at the end of the day", "that being said".

## 4. Signposting and meta-narration
The writing should not announce itself.
"Let's dive in", "Let's explore", "Let's take a look", "In this section we will", "As we can see", "As mentioned earlier", "It is clear that", "The key takeaway is", "What this means is", "Here's the thing", "The bottom line is". Also the "Here's ..." opener family: "Here's how it runs", "Here's the real point", "Here's the part that surprised us", and the standalone labels "What this proves", "Now the contrast that matters" (delete the signpost, lead with the next sentence).

## 5. The colon-elaboration tic
Opening a sentence or a point with "Noun: explanation."
"The core problem: ...", "The result: ...", "The deeper insight: ...", "Bottom line: ...". Rewrite as a normal sentence.

## 6. The antithesis tic
Overused contrast scaffolding.
"It is not just X, it is Y", "This isn't about X. It's about Y", "Not only ... but also". Allowed once per document at most.

## 7. Rule-of-three on autopilot
AI defaults to triples for rhythm.
"fast, cheap, and reliable", "risky, generic, and mediocre". Sometimes two. Sometimes one. A real list of three things is fine. A rhetorical triple every paragraph is not.

## 8. Hype and hollow intensifiers
truly, really, very, incredibly, remarkably, extremely, undoubtedly, powerful, compelling, significant, substantial, standout, unprecedented, revolutionary, transformative, game-changing.

## 9. Transition stuffing
One or two are fine. A wall of them is a tell.
Moreover, Furthermore, Additionally, Notably, Importantly, Consequently, Thus, Hence, Indeed, Ultimately.

## 10. Conclusion cliches
"In conclusion", "To sum up", "In summary" (as an opener), "Ultimately", "At the end of the day", "All in all".

## 11. Cadence and shape (rhythm, not words)
- **Sentence uniformity.** Most sentences the same medium length, no short punches or fragments. This is the loudest tell. Flag any stretch of 4 or more uniform sentences.
- **Over-formatting.** Every point in bold, bullet lists where prose belongs, an emoji in a serious document.
- **Same-length paragraphs** all the way down.
- **"On one hand ... on the other hand"** hedging when a position is wanted.
- **Clipped staccato where flow is better.** Two short sentences chopped apart ("It used to be a shortcut. Now it is a liability.") when one flowing line reads better joined ("It used to be a shortcut but now it's a liability."). Flow beats grammatical tidiness. Read it aloud.
- **List severed into a fragment (hard tell, NOT deliberate punch).** A noun list chopped off its own sentence and dropped as a standalone fragment: "...20 to 30 deliverables into twelve months. Essays, case analyses, memos, final projects." Fold it back into the sentence as an appositive in parentheses or commas: "...20 to 30 deliverables (essays, case analyses, memos, final projects) into twelve months." Flag every one of these, no exceptions.
- **Weak clauses chopped where they should flow.** Two or more flat observations chopped into separate short sentences ("The deadlines stack. And the stakes aren't trivial.") when they should fold into one line with a consequence ("..., which is a huge commitment of time, energy, and focus."). A short sentence must EARN its full stop with real emphasis. Default to flagging staccato, not excusing it as "deliberate punch"; keep a fragment only when the emphasis is genuinely earned. Be stricter here than a first read wants to be.

## 12. Hedging when an opinion is wanted
"It depends", "There are many factors", "Both have their merits", "It is a complex issue", used to dodge taking a position. Take the position unless the tradeoff itself is the point.

## 13. From Wikipedia's "Signs of AI writing" (added 2026-06-25)
Source: en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing. A large catalog the slop-checker also scans against. Some overlap with the above; the extras still get flagged.

- **More overused words:** additionally, boasts, bolstered, garner, interplay, meticulous, meticulously, enduring, vibrant, align with, foster, fostering, showcase, showcasing, enhance, enhancing, highlight, highlighting, emphasizing, valuable, key (as filler), landscape, testament, underscore, tapestry, intricate, intricacies.
- **Significance and legacy padding (a major essay tell):** "stands as a testament to", "serves as a reminder", "plays a vital / significant / crucial / pivotal / key role", "underscores its importance", "highlights the significance of", "reflects a broader", "symbolizing its enduring", "contributing to the", "setting the stage for", "marks a turning point", "leaves an indelible mark", "deeply rooted", "rich tapestry", "evolving landscape", "focal point".
- **Fake authority / vague attribution:** "industry reports", "observers have cited", "experts argue", "some critics argue", "studies show", "several sources", "it is widely regarded". Cite a real source or drop the claim.
- **Promotional / travel-guide / press-release tone:** "boasts a", "nestled in", "in the heart of", "renowned", "groundbreaking", "diverse array", "natural beauty", "commitment to", "dedication to". That is advertising, not analysis.
- **Avoiding plain "is/are":** swapping "is" for "serves as", "stands as", "represents", "boasts", "features", "offers" to sound grand. Use "is" when you mean is.
- **Negative parallelism, all variants:** "not just X, but Y", "not only X but also Y", "not a X but a Y", "X rather than Y", "no X, no Y, just Z". One at most per document.
- **Elegant variation:** swapping in synonyms only to avoid repeating a word. Repeating the right word is fine.
- **Formulaic outline endings:** tacked-on "Challenges", "Future Outlook", "Legacy", "Despite its challenges" sections built from a template instead of the argument.
- **Formatting tells:** Title Case In Headings (use sentence case), bold on every other phrase, curly/smart quotes where straight ones belong, em dashes scattered for emphasis, emoji as section breaks, a horizontal rule jammed before every heading, decorative blockquote or callout boxes for a "Note:" aside (the vertical side-bar in rendered output) where plain text would do.
- **Fabrication tells (zero tolerance):** invented citations, fake or mismatched DOIs and ISBNs, dead links, book citations with no page or URL, and leftover model artifacts in the text (for example "contentReference", "oaicite", ":::", "+1"). If a source or number is not real, do not write it. Flag [NEEDS SOURCE] instead.

(The source also lists Wikipedia-platform tells like broken wikitext, made-up WP: shortcuts, and AfC submission statements. Those rarely apply to an essay.)

## 14. Missing contractions (a quiet tell)
Formal writing that never contracts reads stiff and machine-made. Humans contract, even in academic prose. Flag uncontracted forms where a contraction is natural:
"it is" to "it's", "that is" to "that's", "there is" to "there's", "do not" to "don't", "does not" to "doesn't", "is not" to "isn't", "are not" to "aren't", "cannot" to "can't", "will not" to "won't", "we are" to "we're", "you are" to "you're", "they have" to "they've". Keep the full form only when the sentence leans on it for emphasis.

---

## 15. Formatting and document tells (scan the FINAL exported file, not just the prose)
These are the loudest giveaways in a submitted document and the easiest for a grader to spot at a glance. They come from how AI tools format and export, and from markdown leaking through. Source: Wikipedia "Signs of AI writing" plus academic-integrity and editor guides (researched 2026-06-25).

**Punctuation and characters (convert all to plain):**
- Em dashes (the long dash) used mid-sentence, especially more than rarely. The single most notorious tell. Use commas, parentheses, or a colon.
- En dashes standing in for an em dash.
- Curly / smart quotes and curly apostrophes. Use straight quotes.
- The single-glyph ellipsis. Use three periods.
- Stray non-breaking or special Unicode spaces.

**Layout:**
- Horizontal rules / divider lines between sections. Humans don't do this in essays; AI does it constantly. Remove them.
- Headings in a different font, size, or weight from the body, or Title Case In Headings. Make headings the same font and size as the body, set apart by bold and/or underline only.
- Bold overuse: bolding a lead-in term on every bullet ("**Term:** description"), or bold scattered for emphasis. A list of "**Bold:** text" bullets is one of the loudest structural tells. De-bold them.
- Emoji as bullets or section markers. Remove.
- Over-bulleting where prose belongs; an essay that's mostly bullets. Prefer paragraphs.
- Perfectly uniform paragraph length and spacing.

**Markdown / artifact leaks (smoking-gun tells, zero tolerance):**
- Literal `**`, `##`, or backticks that should have rendered but appear as raw text in the final file.
- Model citation artifacts: contentReference, oaicite, oai_citation, :contentReference, ":::", "+1", turn0search, grok_card.
- Leftover placeholders: "[insert X]", "[Your Name]", "[Date]".
- Pasted dark background or off-color text from a chatbot UI. Paste as plain text, then style.

**Chatbot residue (instant fail if left in):**
- "Certainly!", "Sure!", "Of course!" openers; "As an AI language model"; knowledge-cutoff disclaimers; "As you can see", "I hope this helps", "Let me know if"; restating the prompt back as the thesis.

## 16. The human-document format (apply to every exported deliverable)
Unless the assignment says otherwise, export the deliverable to look like a human wrote it in Word, in the format a one-year MBA program (RUNI) expects:
- **Font: David, 12pt** (David Libre is the open-source equivalent and renders identically in a PDF).
- **Line spacing: 1.5.**
- **Alignment: justified** (both edges).
- **Headings: the same font and 12pt size as the body**, set apart by bold and/or underline only. Never a bigger or different heading font.
- **No horizontal rules, no bold-bullet lead-ins, straight quotes, no em dashes.**

The exact export template and print recipe are in [pdf-export.md](pdf-export.md).

## When NOT to flag (avoid false positives)
- A banned word inside a direct quote or a real source title.
- A technical term used correctly (for example "leverage" in a finance ratio, or "vertical" naming a real market segment) where no plainer word fits.
- A genuine list of three real items, not a rhetorical flourish.
- A single transition word doing honest work.

Flag with judgment. The goal is writing that sounds like a sharp human, not a robot that fears every adjective.
