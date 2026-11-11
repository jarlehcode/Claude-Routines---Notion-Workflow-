---
name: file-journal
description: Files a note classified as Journal into the Journalising database in Notion, assigns it to a journal category, and adds a new feedback entry to that category's page that compares the note with earlier notes and earlier feedback. Also handles adding and retiring journal categories. Use this whenever the incoming note is a reflection, observation, lesson or training note rather than a task or a project idea.
---

# File a journal note and update its category feedback

Two databases are involved:

- **Journalising** (`collection://1e5fc2d1-75e5-812b-ba47-000b9a97e082`): one page per note. Property `Category` is a relation to Journal Categories.
- **Journal Categories** (`collection://209be088-1b72-4be7-a2c4-1d9f35419c7e`): one page per category, with `Name`, `Description` (one line on what belongs there) and `Archived` (checkbox). The body of each category page is the feedback log for that category. `Notes` is the automatic back-link from Journalising; it fills itself in when you set `Category` on a note, so never write to it directly.

## Step 1: Pick the category

1. Query Journal Categories for pages where `Archived` is unchecked. Read each `Name` and `Description`.
2. Assign the note to the single best-fitting category. Prefer an existing one: a slightly loose fit is better than a new category, because feedback only becomes useful when a category collects many notes.
3. Create a new category only when no existing one fits and the topic is likely to come up again. Give it a short name, write a one-line `Description`, and leave the body empty.

## Step 2: File the note

Create one page in Journalising:

- `Name`: the title you wrote for this note.
- `Category`: the category page from step 1.
- Body: the full note, verbatim, and nothing else. Your feedback goes on the category page, not on the note.

Leave `Memory` and `Archive` unchecked; the "All entries" view only shows pages where both are unchecked.

## Step 3: Write the feedback entry

Read before writing:

1. Fetch the category page. Read the three most recent feedback entries (newest are at the top).
2. Query Journalising for the 20 most recent notes in this category, newest first, and read them.

Then insert a new entry **at the start** of the category page, using this structure:

```
## YYYY-MM-DD: <short title of the new note>

**New in this note:** what it adds that earlier notes did not say.

**Against earlier notes:** patterns it repeats, things it contradicts, things that keep coming back without changing.

**Since the last feedback:** better, the same, or worse than what the previous entry described, with the specific notes that show it. If the previous entry gave a suggestion, say whether the notes show it was acted on.

**Next step:** one concrete thing to try.
```

How to write it:

- Compare, do not summarise. The value of the entry is the comparison with earlier notes and earlier feedback, so every entry must refer to at least one earlier note or the previous entry. If this is the first note in the category, say that there is nothing to compare yet and keep the entry to two lines.
- Be direct and specific. Point at what the notes say, quote short phrases from them, and say plainly when nothing has changed.
- Stay with what the notes show. Do not diagnose medical or psychological conditions.
- Write in the language of the note.

The log is append-only. Never edit, shorten or remove an older entry: the older entries are the record that later feedback is measured against.

## Step 4: Category upkeep (at most one change per run)

Only when the evidence is clear:

- **Merge**: two categories keep receiving the same kind of note. Set the `Category` relation of the affected notes to the category you keep, then check `Archived` on the other one.
- **Retire**: a category has had no new notes for a long time and holds fewer than three. Move its notes to the closest category by changing their `Category` relation, then check `Archived`.

Retiring means checking `Archived`. Never delete a category page or its feedback log. After a merge or retire, add a one-line entry at the start of both category pages saying what was changed and why.
