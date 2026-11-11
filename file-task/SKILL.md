---
name: file-task
description: Files a note classified as a Task into the Master Task Database in Notion, with a due date, a task type and a Today/Later label. Use this whenever the incoming note is something concrete the user has to do.
---

# File a task

Create exactly one page in **Master Task Database** (`collection://1e3fc2d1-75e5-81cb-8ae6-000b49081b1d`). Add nothing else: no analysis, no sub-tasks, no comments.

## Properties to set

| Property | Value |
|---|---|
| `Name` | The title you wrote for this note. For a task, start with the action ("Betale husleie", "Book dentist"). |
| `Status` | "Not started 👀" |
| `Due` | A date. See below. |
| `Task Type` | One or two of: Health, Goals, Personal, Finance, Work, Relationships. |
| `Type of To-Do` | "Today To-Do" or "Later To-Do". See below. |

Set all five. The task lists in Task Manager only show pages that have a `Status` and a `Type of To-Do`, so a page missing either one is created but invisible. Leave every other property alone.

## Page body

The full note, verbatim, and nothing else.

## Choosing the due date

Use today's date from the routine prompt as the reference point.

1. If the note states a date or a relative time ("fredag", "tomorrow", "next week"), use it. A weekday means its next occurrence.
2. Otherwise estimate from the content:
   - Urgent wording, or something that loses its point if delayed (a booking, a reply someone is waiting for): today.
   - An ordinary errand: 3 days from today.
   - Something with no time pressure: 7 days from today.

The estimate is a starting point the user will adjust, so pick one date and move on. Do not ask.

## Choosing Type of To-Do

- Due date is today: "Today To-Do".
- Due date is later: "Later To-Do".

Do not use the other options in that property. They are set by hand.

## Choosing Task Type

Pick the one type that fits best. Add a second only when the task clearly belongs to both (a gym payment is Health and Finance). If nothing fits, use Personal.
