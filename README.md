# AI Arcade Lab — One Brief, Nine Games

A bilingual (English / Tiếng Việt) landing page indexing nine arcade games. Nine runs across seven frontier AI models, all given one identical prompt.

Model identities start hidden: the page is a **blind test**. You can guess which model made which game, then reveal the answers and see your score.

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
├── index.html          Landing page (EN / VI, responsive, blind test)
├── .nojekyll           Tells GitHub Pages to serve files as-is
├── README.md
└── games/
    ├── 01-umbra.html
    ├── 02-thrum.html
    ├── 03-cloud-cover.html
    ├── 04-axisonance.html
    ├── 05-rift.html
    ├── 06-foldlight.html
    ├── 07-afterlight.html
    ├── 08-chrono-tether.html
    └── 09-singularis.html
```

The files in `games/` are byte-for-byte copies of the originals. They are named after the **game**, never the model — a model name in the URL would give the blind test away on hover.

| Original filename | Published as | Answer |
| --- | --- | --- |
| `Fable 5.1 Max (Axiom).html` | `games/01-umbra.html` | Fable 5.1 Max · Claude Code · Axiom |
| `Opus 5 Max (Axiom).html` | `games/02-thrum.html` | Opus 5 Max · Claude Code · Axiom |
| `Fable 5.1 Max (Dogma).html` | `games/03-cloud-cover.html` | Fable 5.1 Max · Claude Code · Dogma |
| `Sol 5.6 Max (Axiom).html` | `games/04-axisonance.html` | Sol 5.6 Max · Codex · Axiom |
| `Astra Max (Axiom).html` | `games/05-rift.html` | Astra Max · Codex · Axiom |
| `Astra Max (Dogma).html` | `games/06-foldlight.html` | Astra Max · Codex · Dogma |
| `GPT 6 Pro.html` | `games/07-afterlight.html` | GPT 6 Pro · ChatGPT (Pro) · no system |
| `Gemini 3.1 Pro.html` | `games/08-chrono-tether.html` | Gemini 3.1 Pro · no system |
| `Gemini 3.8 Flash.html` | `games/09-singularis.html` | Gemini 3.8 Flash · no system |

---

## What makes this a controlled experiment

Two models were each run **twice on the same platform at the same effort, with only the discipline system changed** — which gives two genuinely controlled comparisons of Axiom against Dogma:

| Model | Platform | Axiom | Dogma |
| --- | --- | --- | --- |
| Fable 5.1 Max | Claude Code | `01 · UMBRA` | `03 · Cloud Cover` |
| Astra Max | Codex | `05 · RIFT` | `06 · FOLDLIGHT` |

Astra then appears a **third** time as **GPT 6 Pro on ChatGPT** (`07 · AFTERLIGHT`) — a tier available only on Pro accounts, with a very small weekly quota and a different way of reasoning from Astra on Codex.

The most striking result: **Fable 5.1 Max invented a shadow-casting mechanic under both systems** — once as a silent abstract field of light (UMBRA), once as a sunlit afternoon of melting ice cream (Cloud Cover).

---

## Deploying to GitHub Pages

**1. Create a repository** on GitHub (public, no README — this folder already has one).

**2. Push the contents of this folder to the repository root.** From inside `ai-arcade-lab/`:

```bash
git init
git add .
git commit -m "AI Arcade Lab: nine runs, one brief"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

**3. Turn on Pages.** In the repository, go to **Settings → Pages**, set **Source** to `Deploy from a branch`, choose branch `main` and folder `/ (root)`, then **Save**.

Your site goes live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

> Push the **contents** of this folder, not the folder itself. `index.html` must sit at the repository root, otherwise Pages will show a 404.

---

## Notes

- Fully self-contained: no CDN, no webfonts, no build step, no dependencies. Works offline and from `file://`.
- **Language** has three states — `EN`, `EN+VI` (default) and `VI`. Vietnamese is set in Georgia serif throughout, so the two languages stay visually distinct when shown together. Your choice is remembered.
- **Blind test.** Model names, system badges, the filter bar and the roster's Game column are all hidden until you press *Reveal the answers*. Guesses and reveal state persist in `localStorage` (`aal-state-v2`).
- Without JavaScript the page degrades to the fully revealed, bilingual state — everything is readable, only the guessing game is unavailable.
- Each game tile carries a hand-drawn animated SVG poster in that game's own palette. Nothing is loaded over the network.
- Games open in a new tab so the gallery stays where you left it.
- Honours `prefers-reduced-motion`; tested at 360px through 1440px.

---

## Setup terminology

**Axiom** is a plugin the author built and uses for all of their tasks — a fixed sequence of steps the author defined, through which the AI delegates work out to agents. A strict discipline system. *(4 entries)*

**Dogma** is a skill the author created recently, built on six short core philosophies, where the author hands full decision-making authority to the AI. *(2 entries)*

They are two different concepts: one is a tightly structured system, the other is a philosophy that gives the AI full autonomy.
