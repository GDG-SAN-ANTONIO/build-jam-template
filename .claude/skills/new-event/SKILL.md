---
name: new-event
description: Fill all core {{PLACEHOLDER}} tokens for a new event. Prompts for event name, tagline, date, organizer, and repo slug, then patches every file in one pass.
---

# new-event

Collect the following values from the user. Ask for all of them in one message if they haven't been provided:

| Token | Prompt |
|---|---|
| `{{EVENT_NAME}}` | What's the event name? (e.g. "Winter Build Jam") |
| `{{EVENT_TAGLINE}}` | Short tagline for the hero? (e.g. "Build with AI. Together. In two hours.") |
| `{{EVENT_DATE}}` | Date? (e.g. "January 16") — or say "calculate" to run update-date logic |
| `{{EVENT_LOCATION}}` | Venue? (default: "Geekdom, San Antonio" — press enter to keep) |
| `{{ORGANIZER_NAME}}` | Organizer name? (e.g. "GDG San Antonio") |
| `{{ORGANIZER_GITHUB}}` | GitHub org slug? (e.g. "gdg-san-antonio") |
| `{{REPO_SLUG}}` | Repo name slug? (e.g. "winter-build-jam") |
| `{{EVENT_THEME}}` | Event theme? (e.g. "Civic AI") — or "none" to skip |

If the user says "keep" or leaves `{{EVENT_LOCATION}}` blank, set it to "Geekdom, San Antonio".
If `{{EVENT_THEME}}` is "none", leave the token as-is — it will be handled by the THEME OPTIONAL comments.

## Replace tokens in all files

For each token that has a real value (not "none" / blank):
- Replace every occurrence across: `README.md`, `docs/index.html`, `docs/codelab.html`, `docs/resources.html`, `docs/talk.html`, `docs/slide-run-command.html`
- Use Read then Edit tools. Do NOT use shell substitution.
- Replace ALL occurrences in each file (use replace_all: true).

## Confirm

Print a summary table showing each token and the value it was set to.
Note any tokens that were skipped (set to "none").
Remind the user that tracks still need to be added with `/add-tracks`.
