# {{EVENT_NAME}} — {{ORGANIZER_NAME}}

**{{EVENT_TAGLINE}}**

<!-- TRACKS OPTIONAL: Remove the paragraph and table below for code-along events with no tracks -->
Choose a track, open the kit, and ship a real AI prototype for your community.

---

## Before You Arrive

Install these four things so you're ready to go the moment the jam starts:

| Tool | Where to get it |
|---|---|
| **Antigravity** | [antigravity.google/download](https://antigravity.google/download) |
| **uv** (Python manager) | [astral.sh/uv](https://astral.sh/uv) |
| **Git + GitHub account** | [git-scm.com](https://git-scm.com) |
| **Free Gemini API key** | [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey) — free tier covers the whole jam |

---

## Run a Kit in 90 Seconds

**Option A — Antigravity (no terminal needed)**

Open Antigravity and paste this prompt:

```
I'm at {{EVENT_NAME}}. Help me get set up:
1. Check if uv is installed — if not, show me how to install it from astral.sh/uv
2. Check if git is installed — if not, show me how to install it from git-scm.com
3. Clone https://github.com/{{ORGANIZER_GITHUB}}/{{REPO_SLUG}}.git
4. Open the tracks/ folder and tell me what each track does so I can pick one
```

Antigravity will walk you through each step in plain language and run the commands for you.

**Option B — Terminal**

```bash
# 1. Clone this repo
git clone https://github.com/{{ORGANIZER_GITHUB}}/{{REPO_SLUG}}.git

# 2. Go into your chosen track folder
cd {{REPO_SLUG}}/tracks/{{TRACK_1_NAME}}

# 3. Add your free Gemini key
cp .env.example .env
# open .env and paste your key next to GEMINI_API_KEY=

# 4. Go
uv run app.py
```

---

<!-- TRACKS OPTIONAL: Remove this entire section for code-along events with no tracks -->
## Pick Your Track

| # | Track | What you'll build |
|---|---|---|
| 01 | **{{TRACK_1_NAME}}** | {{TRACK_1_DESC}} |
| 02 | **{{TRACK_2_NAME}}** | {{TRACK_2_DESC}} |
<!-- Add or remove rows to match the number of tracks for this event -->
| 🌟 | **Your Idea** | No track? No problem. Use the codelab's spec builder to describe your community problem and let Antigravity build it with you |

Each track folder contains:
- `SPEC.md` — what to build and why
- `app.py` — starter Python script wired to the Gemini API
- `.env.example` — copy this to `.env` and add your key
- `requirements.txt` — all dependencies

---

## Step-by-Step Codelab

Follow the full guided walkthrough at the event site:
👉 **[{{CODELAB_URL}}]({{CODELAB_URL}})**

It walks you through:
1. Installing Antigravity
2. Installing uv and git
3. Cloning this repo and picking a track
4. The Spec Talk — aligning the AI on what to build
5. Generating 3 design docs (product, UI, engineering)
6. Implementing and testing with AI
7. Wiring up your Gemini API key
8. Previewing, verifying, and shipping

---

## Event Details

**{{EVENT_DATE}} · {{EVENT_LOCATION}}**
Hosted by {{ORGANIZER_NAME}}

Bring a laptop and an idea. Drop-ins welcome. The free Gemini API tier covers everything you need for the full jam.

---

## License

MIT — build on it, fork it, take it home.
