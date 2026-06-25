# Build Jam Template — CLAUDE.md

## What this repo is

A reusable template for running community AI build nights, extracted from the
[GDG San Antonio Juneteenth Build Jam](https://github.com/GDG-SAN-ANTONIO/juneteenth-build-jam)
(June 19, live site: gdg-san-antonio.github.io/juneteenth-build-jam).

The goal is a clean, event-agnostic scaffold that can be forked and customized
for any future build jam or hackathon night. Event-specific content has been
replaced with `{{PLACEHOLDER}}` tokens (see **Placeholders** below).

## Repo structure

```
build-jam-template/
├── CLAUDE.md               ← you are here
├── README.md               ← event overview, setup instructions (placeholders)
├── docs/                   ← GitHub Pages site
│   ├── index.html          ← landing page / event site
│   ├── codelab.html        ← step-by-step participant guide
│   ├── resources.html      ← links, tools, references
│   ├── talk.html           ← OPTIONAL — speaker slide companion (omit if no talk)
│   └── slide-run-command.html  ← OPTIONAL — omit if no talk
└── tracks/                 ← OPTIONAL — only present when the event has tracks
    └── {{TRACK_NAME}}/
        ├── SPEC.md         ← problem statement and success criteria
        ├── starter.py      ← Python starter script (Gemini API)
        ├── .env.example    ← environment variable template
        └── requirements.txt
```

> **Event formats vary.** Not every event has a theme or tracks. Some nights are
> a single code-along with no track selection. The template adapts — only include
> the sections and files that apply to the event format being configured.

## Placeholder tokens

All event-specific strings use `{{DOUBLE_BRACES}}` so they are grep-able.

| Token | Replace with |
|---|---|
| `{{EVENT_NAME}}` | Full event name, e.g. "Winter Build Jam" |
| `{{EVENT_TAGLINE}}` | Short tagline shown in hero section |
| `{{EVENT_DATE}}` | Human-readable date, e.g. "February 8" |
| `{{EVENT_LOCATION}}` | Venue name and city |
| `{{ORGANIZER_NAME}}` | GDG chapter or org name |
| `{{ORGANIZER_GITHUB}}` | GitHub org slug, e.g. `gdg-san-antonio` |
| `{{REPO_SLUG}}` | Repo name slug, e.g. `winter-build-jam` |
| `{{EVENT_THEME}}` | Overarching theme, e.g. "Civic AI" — omit entire section if no theme |
| `{{TRACK_N_NAME}}` | Track title (N = 1, 2, … up to however many tracks exist) |
| `{{TRACK_N_DESC}}` | Short track description |
| `{{GEMINI_MODEL}}` | Default model ID, e.g. `gemini-2.0-flash` |
| `{{CODELAB_URL}}` | Full URL to the codelab page |
| `{{GITHUB_KIT_URL}}` | Full URL to this repo |

## Tech stack

- **Frontend:** Plain HTML/CSS (no build step); hosted on GitHub Pages from `docs/`
- **Backend/tracks:** Python only; uses the free [Gemini API](https://aistudio.google.com)
- **Package manager:** `uv`
- **Dev environment:** Antigravity (optional, no-terminal path for participants)

## Event format matrix

| Format | Theme? | Tracks? | `tracks/` folder? |
|---|---|---|---|
| Multi-track jam (e.g. Juneteenth) | Yes | Yes | Yes |
| Themed code-along | Yes | No | No |
| Open build night | No | No | No |
| Custom tracks, no theme | No | Yes | Yes |

Omit any section (theme banner, track cards, tracks/ folder) that doesn't apply.
Never leave placeholder tracks or empty theme sections in a deployed event site.

## How to use this template

1. Fork/copy the repo and rename it to `{{REPO_SLUG}}`
2. Decide the event format (see matrix above)
3. Global find-and-replace all `{{PLACEHOLDER}}` tokens that apply
4. Remove sections and files that don't apply to this event's format
5. Update `docs/index.html` hero image and event branding
6. Enable GitHub Pages (source: `docs/` branch `main`)
7. Test the codelab flow end-to-end before the event

## Origin event — Juneteenth Build Jam

- **Organizer:** GDG San Antonio
- **Date:** June 19, 2025
- **Venue:** Geekdom, San Antonio TX
- **Tracks:** Stand Up Shop · Griot · PlainCare · Speak Up · Block Scan
- **Theme:** Civic AI — participants built prototypes addressing real community
  challenges using the free Gemini API

## Session context for Claude

When working in this repo:
- Preserve all `{{PLACEHOLDER}}` tokens; never substitute real values unless
  the user explicitly provides them
- Themes and tracks are optional — only add those sections/files when the user
  explicitly provides theme or track content; omit them entirely otherwise
- Never generate placeholder track content or dummy theme names; leave those
  sections out until real content is provided
- `talk.html` and `slide-run-command.html` are optional — only include them
  when the event has a speaker talk; omit both otherwise
- Keep HTML files plain (no frameworks, no bundlers)
- Keep Python starter scripts minimal — participants should be able to read and
  modify them in under 10 minutes
- The `docs/` site must work as static files served from GitHub Pages
- Default Gemini model: `gemini-2.0-flash` unless the user specifies otherwise
- License: MIT — keep it
