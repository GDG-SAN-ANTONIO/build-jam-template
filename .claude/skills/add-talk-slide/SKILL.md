---
name: add-talk-slide
description: Append a new slide to talk.html. Supports title slides, principle grids, bullet list slides, and code slides.
---

# add-talk-slide

Ask the user what kind of slide to add:

| Type | Use for |
|---|---|
| `title` | Section divider with big headline |
| `principles` | Grid of 3 or 6 cards (name + description each) |
| `bullets` | Eyebrow + headline + bullet list |
| `code` | Eyebrow + headline + a terminal/code block |
| `custom` | User provides raw HTML for the slide-content div |

Then collect the content for that type.

---

## Build the slide HTML

All slides follow this wrapper:

```html
<div class="slide-panel slide-content" data-slide="N" style="display:none;">
  <!-- slide content here -->
  <div class="slide-foot">
    <span>{{ORGANIZER_NAME}} · {{EVENT_NAME}}</span>
    <span></span>
  </div>
</div>
```

Where `N` = the next slide number (count existing `data-slide` attributes + 1).

### title slide
```html
<p class="slide-eyebrow">[eyebrow]</p>
<h1 class="slide-title">[title]<br><span>[subtitle]</span></h1>
<p class="slide-body">[body text]</p>
```

### principles slide (3-up or 6-up grid)
```html
<p class="slide-eyebrow">[eyebrow]</p>
<h1 class="slide-title" style="font-size:3.5vw;">[title]</h1>
<div class="principles-grid" style="grid-template-columns: repeat([2 or 3], 1fr);">
  <div class="principle-card">
    <div class="principle-num">01</div>
    <div class="principle-title">[name]</div>
    <div class="principle-desc">[desc]</div>
  </div>
  <!-- repeat for each principle -->
</div>
```

### bullets slide
```html
<p class="slide-eyebrow">[eyebrow]</p>
<h1 class="slide-title" style="font-size:3.5vw;">[title]</h1>
<ul class="slide-body" style="padding-left:1.8vw;font-size:1.6vw;line-height:2;">
  <li>[bullet]</li>
  <!-- repeat -->
</ul>
```

### code slide
```html
<p class="slide-eyebrow">[eyebrow]</p>
<h1 class="slide-title" style="font-size:3.2vw;">[title]</h1>
<pre style="background:#090704;border:1px solid var(--line);border-radius:1vw;padding:2vw;font-family:'Space Mono',monospace;font-size:1.3vw;line-height:1.8;color:var(--cream);max-width:80%;margin-top:1.5vw;">[code]</pre>
```

---

## Insert into talk.html

1. Read `docs/talk.html`
2. Find the closing `<!-- Navigation arrows -->` comment
3. Insert the new slide panel immediately before that comment
4. The slide already has `style="display:none;"` — JS handles showing it

---

## Confirm

Report the slide number assigned and the type added.
Remind the user that the progress dots update automatically from the JS — no manual change needed.
