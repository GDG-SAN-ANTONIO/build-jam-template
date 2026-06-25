---
name: add-tracks
description: Add tracks to the event. Populates the trackData JS object in codelab.html, track cards in index.html, and resource sections in resources.html.
---

# add-tracks

Ask the user to provide tracks. For each track collect:
- **Name** (e.g. "Stand Up Shop")
- **Emoji** (e.g. "🛍️")
- **Description** (one sentence)
- **Color** — choose from: `var(--accent)`, `var(--accent-2)`, `var(--gold)`, `var(--cream-dim)`, or a hex value
- **Folder name** (e.g. "01-economic-empowerment") — used in repo paths

Also ask: should the last track be a "Bring Your Own Idea" open track? (yes/no)

The user can provide tracks as a list, one at a time, or in any format — extract the fields.

---

## Update 1: codelab.html — trackData object

Read `docs/codelab.html`. Find the `trackData` block (between the two `// -------` comment lines).

Replace the entire commented-out example block with real track entries:

```js
const trackData = {
  1: {
    name: "Track Name",
    emoji: "🛍️",
    folder: "tracks/01-folder-name",
    desc: "One sentence description.",
    color: "var(--accent)",
    agPrompt: "Clone https://github.com/{{ORGANIZER_GITHUB}}/{{REPO_SLUG}}.git to my Desktop if it isn't there already, then open the tracks/01-folder-name folder as my workspace. Confirm when it's ready.",
    cdPath: "cd ~/Desktop/{{REPO_SLUG}}/tracks/01-folder-name",
    input: ""
  },
  // ... more tracks
};
```

If the user wants a "Bring Your Own" track, append it as the highest-numbered entry with:
- name: "Your Idea", emoji: "🌟", color: "var(--cream-dim)", agPrompt: "", cdPath: "", input: ""

---

## Update 2: index.html — track cards

Read `docs/index.html`. Find the tracks-grid section (between the TRACKS OPTIONAL comments).

Replace the single placeholder `.track-card` div with one card per track:

```html
<div class="track-card" style="--c: [color];">
  <div class="track-card-header">
    <span class="track-emoji">[emoji]</span>
    <div>
      <div class="track-name">[name]</div>
    </div>
  </div>
  <p class="track-desc">[description]</p>
</div>
```

Do NOT add a card for the "Your Idea" open track — it doesn't belong in the landing page grid.

---

## Update 3: resources.html — per-track sections

Read `docs/resources.html`. Find the TRACKS OPTIONAL block.

Replace the single placeholder `.resource-section` with one section per track.
Use this structure for each:

```html
<div class="resource-section">
  <div class="rs-header">
    <p class="rs-tag">[Track Name]</p>
    <h2 class="rs-title">[Track Name] Resources</h2>
    <p class="rs-desc">[description]</p>
  </div>
  <div class="resource-list">
    <div class="resource-item">
      <span class="resource-name">Resource Name</span>
      <span class="resource-desc">Add relevant data sources and tools for this track.</span>
      <a class="resource-link" href="#" target="_blank">link →</a>
    </div>
  </div>
</div>
```

Leave the resource items as stubs — the user will fill in real links separately.

---

## Confirm

Report which files were updated and how many tracks were added.
Remind the user to fill in real resource links in resources.html.
Also remind them to create the track folders under `tracks/` in the repo.
