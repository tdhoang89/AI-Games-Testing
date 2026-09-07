# AI Arcade Lab — One Brief, Eight Models

A bilingual (English / Tiếng Việt) landing page indexing eight arcade games, each written by a different frontier AI model from one identical prompt.

**Live site:** `https://<your-username>.github.io/<repo-name>/`

---

## The brief given to every model

> Create an exceptionally polished, addictive casual arcade game in a single self-contained HTML file.
>
> The core mechanic should be simple enough to understand instantly, but have enough depth to make the player want to keep improving their high score.
>
> Prioritize genuine originality. Invent a fresh core mechanic or interaction that does not feel like a clone, remix, or obvious variation of an existing popular game. Surprise me with something that feels new.
>
> Do not start from a known game genre or familiar mechanic. Invent the game from first principles.
>
> You decide everything else.

No follow-up instructions, no examples, no corrections. Every game is published exactly as its model produced it.

---

## Contents

```
.
├── index.html          Landing page (EN / VI, responsive)
├── .nojekyll           Tells GitHub Pages to serve files as-is
├── README.md
└── games/
    ├── fable-5-1-max-axiom.html    UMBRA
    ├── opus-5-max-axiom.html       THRUM
    ├── sol-5-6-max-axiom.html      AXISONANCE
    ├── astra-max-axiom.html        RIFT
    ├── astra-max-dogma.html        FOLDLIGHT
    ├── gpt-6-pro.html              AFTERLIGHT
    ├── gemini-3-1-pro.html         Chrono Tether
    └── gemini-3-8-flash.html       SINGULARIS
```

The files in `games/` are byte-for-byte copies of the originals, renamed only so the URLs contain no spaces or parentheses. Their contents are untouched.

| Original filename | Published as |
| --- | --- |
| `Fable 5.1 Max (Axiom).html` | `games/fable-5-1-max-axiom.html` |
| `Opus 5 Max (Axiom).html` | `games/opus-5-max-axiom.html` |
| `Sol 5.6 Max (Axiom).html` | `games/sol-5-6-max-axiom.html` |
| `Astra Max (Axiom).html` | `games/astra-max-axiom.html` |
| `Astra Max (Dogma).html` | `games/astra-max-dogma.html` |
| `GPT 6 Pro.html` | `games/gpt-6-pro.html` |
| `Gemini 3.1 Pro.html` | `games/gemini-3-1-pro.html` |
| `Gemini 3.8 Flash.html` | `games/gemini-3-8-flash.html` |

---

## Deploying to GitHub Pages

**1. Create a repository** on GitHub (public, no README — this folder already has one).

**2. Push the contents of this folder to the repository root.** From inside `ai-arcade-lab/`:

```bash
git init
git add .
git commit -m "AI Arcade Lab: eight models, one brief"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

**3. Turn on Pages.** In the repository, go to **Settings → Pages**, set **Source** to `Deploy from a branch`, choose branch `main` and folder `/ (root)`, then **Save**.

Your site goes live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

> Push the **contents** of this folder, not the folder itself. `index.html` must sit at the repository root, otherwise Pages will show a 404.

---

## Notes

- The page is fully self-contained: no CDN, no fonts, no build step, no dependencies. It works offline and from `file://`.
- Language defaults to English, auto-switches to Vietnamese for `vi-*` browsers, and remembers your choice.
- Games open in a new tab so the gallery stays where you left it.
- Tested on desktop and mobile viewports; honours `prefers-reduced-motion`.

---

## Setup terminology

**Axiom** is a plugin the author built and uses for all of their tasks — a fixed sequence of steps the author defined, through which the AI delegates work out to agents. A strict discipline system.

**Dogma** is a skill the author created recently, built on six short core philosophies, where the author hands full decision-making authority to the AI.

They are two different concepts: one is a tightly structured system, the other is a philosophy that gives the AI full autonomy.
