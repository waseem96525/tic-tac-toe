# ⭕ Tic Tac Toe — vs Friend or AI ❌

A polished, installable Tic Tac Toe game. Challenge a friend locally or take on an unbeatable AI. Works offline, fully responsive, no build step.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/waseem96525/tic-tac-toe)

**Live demo:** `https://<your-vercel-project>.vercel.app` _(update after deploying)_

## ✨ Features

- 🤖 **Play vs AI** — 4 difficulties: Easy, Medium, Hard, Unbeatable (minimax + alpha-beta pruning)
- 🧑‍🤝‍🧑 **2-player local mode**, play as ✕ or ○, alternate starter each round
- ↩ **Undo**, 💡 **Hint** (best-move highlight), keyboard shortcuts (`1–9`, `U`, `H`, `N`)
- 📊 Scoreboard with streaks, win %, persistent game history (`localStorage`)
- 🔊 WebAudio sound effects, 🌙 light/dark theme, 🎉 confetti wins
- 📲 **Installable PWA** — manifest + service worker, offline support, iOS/Android/desktop install flow with built-in diagnostics
- 📱 Fully responsive — phones (320px+), tablets, desktop, landscape

## 📁 Project structure

```
tic-tac-toe.html        # the whole app (single file — HTML + CSS + JS)
manifest.webmanifest    # PWA manifest (name, icons, start_url…)
sw.js                   # service worker (offline cache)
icons/icon-192.png      # app icon 192×192
icons/icon-512.png      # app icon 512×512 (+ maskable)
vercel.json             # Vercel rewrites + headers (no-cache for sw.js)
public_tic-tac-toe_diff.html  # original design diff (reference)
```

## ▶️ Run locally

```bash
# from this folder — required for PWA install + service worker
# (browsers block them on file://)
python -m http.server 8000
# open http://localhost:8000/tic-tac-toe.html
```

## 🚀 Deploy on Vercel

**Option A — GitHub import (recommended):**

1. Push this folder to GitHub (`waseem96525/tic-tac-toe`).
2. Go to [vercel.com/new](https://vercel.com/new) → **Import** the repo.
3. Framework preset: **Other**. Build command: _(empty)_. Output: _(root)_.
4. Hit **Deploy** — done. No build step, static files only.

**Option B — Vercel CLI:**

```bash
npm i -g vercel
vercel        # link + preview
vercel --prod # production
```

The root URL `/` rewrites to `/tic-tac-toe.html` (see `vercel.json`), and `sw.js` is served with `Cache-Control: no-cache` so updates reach installed users.

## 📲 PWA install notes

- Must be served over **HTTPS or localhost** — install prompts never fire on `file://`.
- Chrome/Edge: interact with the page once, then tap **⬇ Install App**.
- iOS Safari: Share → **Add to Home Screen** (no automatic prompt on iOS).
- If install shows help instead of the system dialog, expand **“Why am I seeing this?”** in the dialog — it pinpoints the failing check.

## 🛠 Tech

HTML + CSS + vanilla JS. Zero dependencies, zero build.
