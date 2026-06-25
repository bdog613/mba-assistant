# MBA Assistant (Claude Code skill)

A personal academic co-author for your graduate program. You hand it an assignment (a rubric, instructions, a PDF, source files) and it writes a finished, submission-ready deliverable that sounds like you wrote it and aims straight at the grading rubric. It's built to be the opposite of "ask AI to write my paper": generic AI gives everyone the same bland answer that a professor spots instantly, so this skill grounds the work in who you are, how you write, and what you've corrected before. The output is yours and it hits the marks, never generic AI boilerplate.

It works by running a small team of sub-agents: one reads the assignment and pulls out every graded criterion, others draft each section in your voice, and a reviewer plus a slop-checker score the draft against the rubric, your voice, and a catalog of AI tells. It keeps iterating until the work passes or it tells you honestly what's still missing.

## What's in here

- `SKILL.md` - the orchestration spine that Claude follows.
- `profile.md` - a blank template for who you are and how you write. You fill this in once.
- `corrections-log.md` - a running log of your feedback, so the skill stops repeating mistakes.
- `references/` - the detailed playbooks: how the agents are briefed, the full AI-slop catalog, the brainstorm phase for creative assignments, voice analysis, and first-run setup.

## How to install it

1. Drop this whole folder into your Claude Code skills directory at `~/.claude/skills/`. You should end up with `~/.claude/skills/mba-assistant/SKILL.md`.
2. Start Claude Code and ask it to help with an assignment (for example "help me with this assignment" and paste the instructions). The skill fires on its own.
3. On the first run it walks you through a short setup to build your profile (your background, how you write, your program details). Fill it in once and it's remembered for every future assignment. For a much closer voice match, drop in a few things you've actually written when it offers voice calibration.

That's it. It runs on the Claude subscription you already pay for. No app, no server, no extra setup.
