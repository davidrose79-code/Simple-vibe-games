# CLAUDE.md — Instructions for Claude Code

This file tells Claude Code how to work on the Simple Vibe Games project.
Read it fully before making any changes.

---

## What this project is

A vanilla HTML/CSS/JS web arcade — a collection of simple, fun browser games
aimed at players aged 5 and above. The homepage (index.html at the root) is a
clean Apple-inspired launch pad with circular icon buttons linking to each game.

There is no build step, no framework, no bundler. Everything runs by opening a
file in a browser.

---

## Branching strategy

- **main** — production branch, served via GitHub Pages. Never commit directly.
- **dev** — active development branch. All new work starts here.
- **Always work on the `dev` branch** unless explicitly told otherwise.
- When a feature or game is stable and reviewed, it is merged into main.

---

## File structure

```
/
├── index.html          ← Homepage (games hub)
├── style.css           ← Global styles and design tokens
├── CLAUDE.md           ← These instructions
├── README.md           ← Project overview for humans
├── .gitignore
└── games/
    └── [game-name]/
        └── index.html  ← Each game is fully self-contained here
```

Each game lives in its own folder under `/games/`. The folder name is
kebab-case (e.g. `noughts-and-crosses`, `word-search`).

---

## Design principles

Follow these on every file you touch:

1. **No external dependencies** — no CDNs, no npm packages, no frameworks.
   Vanilla HTML5, CSS3, and JavaScript only.
2. **Mobile-first CSS** — write base styles for small screens, then use
   `min-width` media queries to expand for larger viewports.
3. **Semantic HTML5** — use `<main>`, `<nav>`, `<section>`, `<article>`,
   `<header>`, `<footer>` appropriately.
4. **Accessible** — every interactive element needs an `aria-label`.
   Use sufficient colour contrast (WCAG AA). Ensure full keyboard navigation.
   All images need descriptive `alt` text.
5. **Apple aesthetic** — generous whitespace, system font stack, subtle
   box-shadows, smooth CSS transitions (200–300ms ease). No harsh colours.
   Accent colour is a calm blue (`#0071e3`).
6. **Age 5+ readability** — keep labels and instructions short and friendly.
   Prefer large tap targets (minimum 44×44px).
7. **Self-contained games** — each game folder must work independently.
   Do not share JS files between games. Shared CSS can reference `../../style.css`.

### Colour tokens (defined in style.css)

| Token               | Value     | Use                        |
|---------------------|-----------|----------------------------|
| `--color-bg`        | `#ffffff` | Page background            |
| `--color-text`      | `#1d1d1f` | Primary text               |
| `--color-subtle`    | `#6e6e73` | Secondary / muted text     |
| `--color-accent`    | `#0071e3` | Links, focus rings, hover  |
| `--color-surface`   | `#f5f5f7` | Card / circle backgrounds  |
| `--color-shadow`    | `rgba(0,0,0,0.08)` | Subtle elevation   |

---

## How to add a new game

1. **Create the folder**: `games/[kebab-case-name]/`
2. **Create `index.html`** inside it. Use the "coming soon" placeholder as a
   starting point — it already has the correct `<head>`, font stack, and back
   link. Replace the placeholder content with the actual game.
3. **Add a circle button to `index.html`** (root) inside the `<div class="grid">`:

```html
<a href="games/[game-name]/index.html"
   class="game-card"
   aria-label="Play [Game Name]">
  <div class="circle">[emoji]</div>
  <span class="label">[Game Name]</span>
</a>
```

4. **Test** on mobile width first, then desktop.
5. **Commit** to `dev` with a clear message, e.g. `add: snake game`.

---

## Accessibility checklist (run before every commit)

- [ ] All `<a>` and `<button>` elements have `aria-label` or visible text
- [ ] Focus ring is visible on keyboard navigation (never `outline: none` without replacement)
- [ ] Colour contrast passes WCAG AA (4.5:1 for text, 3:1 for large text)
- [ ] Page works at 200% browser zoom
- [ ] Touch targets are at least 44×44px
- [ ] No horizontal scroll on 320px wide viewport

---

## Commit message conventions

```
add: [thing added]
fix: [thing fixed]
update: [thing updated]
remove: [thing removed]
```

Keep the first line under 72 characters. No period at the end.
