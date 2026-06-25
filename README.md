# {{EVENT_NAME}} — {{ORGANIZER_NAME}}

**{{EVENT_TAGLINE}}**

**{{EVENT_DATE}} · {{EVENT_LOCATION}}**

---

## Format Variants

This template supports several event formats. Only the sections that apply to your format are included — remove or skip anything marked optional.

| Format | Tracks? | Talk? | What to keep |
|---|---|---|---|
| Multi-track jam | ✅ | optional | Everything |
| Themed code-along | ❌ | optional | Remove "Pick Your Track" section and `tracks/` folder |
| Open build night | ❌ | ❌ | Remove tracks, talk, and slide files |
| Custom tracks, no theme | ✅ | optional | Remove `{{EVENT_THEME}}` references |

---

## Before You Arrive

Install these four things so you're ready to go the moment the event starts:

| Tool | Where to get it |
|---|---|
| **Antigravity** | [antigravity.google/download](https://antigravity.google/download) |
| **uv** (Python manager) | [astral.sh/uv](https://astral.sh/uv) |
| **Git + GitHub account** | [git-scm.com](https://git-scm.com) |
| **Free Gemini API key** | [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey) — free tier covers the whole event |

---

## Get Started

**Option A — Antigravity (no terminal needed)**

Open Antigravity and paste this prompt:

```
I'm at {{EVENT_NAME}}. Help me get set up:
1. Check if uv is installed — if not, show me how to install it from astral.sh/uv
2. Check if git is installed — if not, show me how to install it from git-scm.com
3. Clone https://github.com/{{ORGANIZER_GITHUB}}/{{REPO_SLUG}}.git
```

<!-- TRACKS OPTIONAL: Add step 4 below for multi-track events -->
<!-- 4. Open the tracks/ folder and tell me what each track does so I can pick one -->

**Option B — Terminal**

```bash
git clone https://github.com/{{ORGANIZER_GITHUB}}/{{REPO_SLUG}}.git
cd {{REPO_SLUG}}
```

<!-- TRACKS OPTIONAL: Replace the cd line above and add the block below for multi-track events
cd {{REPO_SLUG}}/tracks/{{TRACK_1_NAME}}
cp .env.example .env      # add your Gemini key
uv run app.py
-->

---

<!-- TRACKS OPTIONAL: Remove this entire section for code-along or open build night events -->
## Pick Your Track

<!-- Add or remove rows to match the number of tracks for this event -->
| # | Track | What you'll build |
|---|---|---|
| 01 | **{{TRACK_1_NAME}}** | {{TRACK_1_DESC}} |
| 02 | **{{TRACK_2_NAME}}** | {{TRACK_2_DESC}} |
| 🌟 | **Your Idea** | Describe your community problem and let Antigravity build it with you |

Each track folder contains:
- `SPEC.md` — what to build and why
- `app.py` — starter Python script wired to the Gemini API
- `.env.example` — copy this to `.env` and add your key
- `requirements.txt` — all dependencies

---

## Step-by-Step Codelab

Follow the full guided walkthrough at the event site:
👉 **[{{CODELAB_URL}}]({{CODELAB_URL}})**

The codelab walks you through:
1. Installing Antigravity
2. Installing uv and git
3. <!-- TRACKS OPTIONAL: "Picking a track" → replace with "Opening your project folder" for no-track events -->
   Picking a track and opening the kit
4. The Spec Talk — aligning the AI on what to build
5. Generating 3 design docs (product, UI, engineering)
6. Building and testing with AI
7. Wiring up your Gemini API key
8. Running and sharing your app

---

## Event Details

Hosted by **{{ORGANIZER_NAME}}**
Bring a laptop and an idea. Drop-ins welcome. The free Gemini API tier covers everything you need.

---

## License

MIT — build on it, fork it, take it home.

---

> **Template maintainers:** this README is part of the [build-jam-template](https://github.com/GDG-SAN-ANTONIO/build-jam-template).
> Run `/new-event` in Claude Code to configure a fresh copy for your next event.
