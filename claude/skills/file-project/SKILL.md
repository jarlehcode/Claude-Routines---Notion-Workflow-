---
name: file-project
description: Files a note classified as a Project idea into the Projects database in Notion, keeps the original idea untouched, and appends a blunt market-analyst assessment underneath it. Use this whenever the incoming note is an idea for something to build, sell or start.
---

# File a project idea and assess it

Create exactly one page in **Projects** (`collection://1ebfc2d1-75e5-81e6-90bd-000b45f9e6b4`).

## Properties to set

| Property | Value |
|---|---|
| `Project name` | The title you wrote for this note. |
| `Status` | "Review". The Review view in Project Planner only lists pages with this status. |
| `Category` | The closest of: Company, Github, Løsninger, Kjøp/Salg, Skole, Personlig. |
| `Positives / Negatives` | Two or three of each, one short line per point, taken from your analysis. |

Leave `Details`, `Due`, `Owner` and `Tasks` empty.

## Page body

The body has two parts, in this order:

1. **The original idea, verbatim.** No heading, no corrections, no formatting changes. This part belongs to the user and is never touched again.
2. A divider, then your analysis under the heading `## Analysis (Claude, YYYY-MM-DD)`.

If you ever run on a project page that already exists, add your analysis at the end. Never change anything above the divider.

## The analysis

Take the role of a market analyst who is paid to stop bad ideas early. The user wants an honest read, not encouragement: most ideas noted in passing are not worth building, and saying so clearly is the useful outcome.

Cover these, a few lines each:

- **Verdict:** Doable, Partly doable or Not doable, with the single main reason.
- **Who it is for:** who would use or pay for this, and why they might not bother.
- **What already exists:** known alternatives or competitors, and what this idea would have to do better. If you are not sure something exists, say so instead of guessing.
- **What it takes:** skills, time and money for one student working alone with beginner-level programming experience.
- **Most likely reason it fails.**
- **Cheapest test:** one thing that could be done within a week to find out whether the idea deserves more time.

How to write it:

- State the weaknesses first and without softening. No praise unless a specific strength affects the verdict.
- Do not invent market sizes, prices or user numbers. Mark every estimate as an estimate.
- Keep it under 300 words. Write in the language of the idea.
