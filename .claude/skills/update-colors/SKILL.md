---
name: update-colors
description: Swap the color palette across all HTML files. Updates --accent, --accent-2, and --gold CSS variables in each file's :root block.
---

# update-colors

Ask the user for a color scheme. They can provide:

**Option A — Named theme:**
- "Juneteenth" → accent: #CE1126, accent-2: #009A44, gold: #E8A33D (Pan-African red/green/gold)
- "GDG" → accent: #4285F4, accent-2: #34A853, gold: #FBBC05 (Google blue/green/yellow)
- "Ocean" → accent: #0077B6, accent-2: #00B4D8, gold: #90E0EF
- "Sunset" → accent: #E63946, accent-2: #F4A261, gold: #E9C46A

**Option B — Custom hex values:**
- Primary accent (buttons, links, active states)
- Secondary accent (success states, tips)
- Gold (eyebrow labels, highlights)

---

## Update :root in all HTML files

Files to update: `docs/index.html`, `docs/codelab.html`, `docs/resources.html`, `docs/talk.html`, `docs/slide-run-command.html`

For each file:
1. Read the file
2. Find the `:root {` block
3. Replace the values for `--accent`, `--accent-2`, and `--gold`

In `docs/slide-run-command.html` the variables are named differently (`--clay`, `--gold`, `--green`) — map them:
- `--clay` → primary accent
- `--green` → secondary accent  
- `--gold` → gold

Use Edit with replace_all: false, targeting the specific line in each :root block.

---

## Confirm

Print a color swatch summary showing the old → new values for each variable.
Note the slide-run-command.html variable name mapping so the user understands what changed.
