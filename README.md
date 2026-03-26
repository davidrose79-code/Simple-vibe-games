# Simple Vibe Games

A clean, Apple-inspired arcade of simple browser games — no login, no download,
no friction. Just open and play.

Designed for everyone aged 5 and above.

---

## Play it

**Live site:** [davidrose79-code.github.io/Simple-vibe-games](https://davidrose79-code.github.io/Simple-vibe-games/)

Or run it locally — open `index.html` in any modern browser. No server required.

If you have Python installed you can also run a quick local server:

```bash
# Python 3
python -m http.server 8080
# then open http://localhost:8080
```

---

## Games

| Game | Status | Folder |
|------|--------|--------|
| Noughts and Crosses | Live | `games/noughts-and-crosses/` |
| Memory Cards | Live | `games/memory-cards/` |
| Word Search | Live | `games/word-search/` |
| Minesweeper | Coming soon | `games/minesweeper/` |
| Hangman | Live | `games/hangman/` |
| Snake | Planned | — |

---

## Tech stack

- **HTML5** — semantic markup
- **CSS3** — custom properties, flexbox, grid, transitions
- **Vanilla JavaScript** — no frameworks, no build step, no bundler

Everything runs directly in the browser. There is nothing to install.

---

## Project structure

```
/
├── index.html        ← Games hub homepage
├── style.css         ← Global design tokens and shared styles
├── CLAUDE.md         ← Instructions for Claude Code
└── games/
    └── [game-name]/
        └── index.html
```

---

## Contributing

1. All development happens on the **`dev`** branch.
2. Create your feature branch from `dev`.
3. Open a pull request back into `dev` when ready.
4. Stable `dev` changes are merged into **`main`** (served via GitHub Pages).

See `CLAUDE.md` for full design principles and coding conventions.

---

## Licence

MIT
