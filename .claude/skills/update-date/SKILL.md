---
name: update-date
description: Given a month and year, calculates the 3rd Friday and patches {{EVENT_DATE}} across all template files. GDG SA buildnights are always the 3rd Friday of the month at Geekdom.
---

# update-date

The user will provide a month and year (e.g. "July 2026" or just "July").
If no year is given, use the current year.

## Step 1 — Calculate the 3rd Friday

Find the 3rd Friday of the given month:
1. Determine the day of the week for the 1st of that month.
2. Find the first Friday (day 5, where Monday=0).
3. The 3rd Friday = first Friday + 14 days.
4. Format as a human-readable date, e.g. "Friday, July 17" or "July 18, 2025".

Use this format for `{{EVENT_DATE}}`: `[Month] [Day]` — e.g. `July 18`.

## Step 2 — Replace {{EVENT_DATE}} in all files

Find and replace every occurrence of `{{EVENT_DATE}}` with the calculated date in:
- `README.md`
- `docs/index.html`
- `docs/codelab.html`
- `docs/resources.html`
- `docs/talk.html` (if it exists)
- `docs/slide-run-command.html`

Use the Read then Edit tools — do NOT use sed or shell substitution.

## Step 3 — Confirm

Report:
- The calculated date
- How many files were updated
- Any files where `{{EVENT_DATE}}` was not found (so the user knows if something was already filled in)

Do NOT change `{{EVENT_LOCATION}}` — it is always "Geekdom, San Antonio" and will be hardcoded separately.
