# Vembanattu-OP Dyno 🦖

A custom Chrome Dino endless-runner game — the original Chromium dino engine with
custom jump & game-over sounds. Pure HTML/CSS/JS, no frameworks, no build step.

**Sounds**
- Jump → `sounds/vembanadu-jump.mp3`
- Game over → `sounds/vembanadu-game-over.mp3`
- Every 100 points → classic dino milestone blip

---

## Run locally

Any static file server works. From this folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000 and press **Space** to play.

> Open `index.html` directly with `file://` and it will still work in most
> browsers, but a local server is recommended so sounds always load.

---

## Deploy to Vercel (zero config)

### Option A — GitHub (recommended, auto-deploys on every push)

1. Create a new repo on GitHub (e.g. `vembanattu-op-dyno`).
2. Click **uploading an existing file** and drag **all files from this folder**
   (index.html, script.js, icon-32.png, assets/, sounds/, README.md) into the
   upload box, then commit.
3. Go to https://vercel.com/new → **Import** the repo.
4. Framework Preset: **Other** (leave everything else as default — no build
   command, output directory `./`).
5. Click **Deploy**. Done — your game is live on `*.vercel.app`.

### Option B — Vercel CLI

```bash
npm i -g vercel
cd vembanattu-op-dyno
vercel --prod
```

### Option C — drag & drop

Extract this zip, then drag the folder into https://vercel.com/new
(also works on Netlify's drop page).

---

## File map

```
index.html          game page (title, UI, sound wiring)
script.js           game engine (Chromium dino, patched to run on any domain)
icon-32.png         favicon
assets/
  index-lFZlcDO7.css       site stylesheet
  default_100_percent/     1x spritesheet + offline icon
  default_200_percent/     2x (Retina) spritesheet + offline icon
  sounds/                  milestone blip + fallback jump/hit sounds
sounds/
  vembanadu-jump.mp3       your jump sound
  vembanadu-game-over.mp3  your game-over sound
```

## Customizing

- **Change the name** — edit the `<title>` and headings in `index.html`.
- **Change sounds** — replace the MP3s in `sounds/` (same filenames) or update
  the two `src` paths inside `<template id="audio-resources">` in `index.html`.

Have fun! 🎮
