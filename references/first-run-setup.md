# First-Run Setup

Run this **only** when `profile.md` is missing, empty, a blank template, or `confirmed: false`. Goal: end with a `profile.md` you've verified and marked `confirmed: true`. After that, the skill never runs this again unless asked.

The template ships with a blank `profile.md` (all `[bracketed placeholders]`, `confirmed: false`), so on a fresh install you'll almost always be in Case B below.

The guiding rule: **learn the voice from your real writing, not from your biography.** Lead with writing samples and writing rules. Personal background is optional and comes last, only if you want to add it.

## Case B: a blank or new profile (the normal first run)

Build the profile from your writing, in this order. The skill batches the asks, but it leads with the samples and treats background as optional.

1. **Your previous writing. This is the main input, asked first.**
   > Paste or drop in a few things you've written. Past graded assignments are best, but essays, memos, or long emails work too. Even one helps. I'll learn how you actually write from these, not from a description of it.

   The skill runs [voice-analysis.md](voice-analysis.md) on whatever you share and fills the Voice fingerprint. This is the primary signal. If you truly have nothing to share, it'll ask you to describe your writing instead, but real samples beat any description.

2. **Specific writing instructions.**
   > Any hard rules for your writing? For example: no em dashes, formal or conversational, a target reading level, a citation style, anything you always want or never want.

   These become your voice rules. The skill also grabs two practical basics to aim the work: your grade target (top of class or a solid pass) and whether assignments are graded solo or as a group.

3. **Personal background. Optional, last, and only if you want it.**
   > Optional: if you think it helps the work sound like you, tell me a bit about your background, what you do, what you know well. It gives the writing a point of view on open-ended prompts. Totally fine to skip.

   The background and lens only get filled if you offer them. Skip it and your samples and rules carry the voice. The skill never pushes for it.

Then it writes `profile.md`, sets `confirmed: true`, and continues. It won't lead with biography, and a blank background is not a problem.

## Case A: profile.md already has real content but is `confirmed: false`

If you carried over a profile or filled some of it in but haven't verified it:
1. The skill shows it in the chat, readably.
2. It points at any remaining placeholder or **(confirm)** line and asks you to fill or correct those, batched into one message.
3. It offers the voice calibration below, then sets `confirmed: true` and continues.

## Voice calibration from real writing (the highest-value step)
Real samples are the single biggest lever for matching your voice. Rules get the writing close, samples get it right. Whenever you give samples, at setup or any time later, the skill runs [voice-analysis.md](voice-analysis.md) and fills the Voice fingerprint section of `profile.md`. It always offers this, and never blocks the work on it.

## Importing context from a prior chat
The skill can't read claude.ai web chat history directly. If you want to carry over context, paste the relevant part. The skill folds the stable preferences (not the one-off details) into `profile.md`, confirms, and continues.
