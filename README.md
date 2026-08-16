# 64 Squares — a complete chess app

A single-page chess app: two-player pass-and-play, plus a single-player mode
against an AI that scales from 800 to 2400 ELO. Everything runs client-side —
no server, no accounts, no ads. Your rating and game history are saved on your
device (localStorage), and once installed it works offline.

## What's inside
- `index.html` — the entire app (board, rules engine, AI, clock, PGN, themes). This is the only file the app truly needs.
- `manifest.json` — lets iPad/Android offer "Add to Home Screen" as a proper app.
- `sw.js` — a small service worker that caches the app so it still opens with no signal.
- `icons/` — home-screen icons.

## Features
- **Full rules engine**: legal move generation, check/checkmate/stalemate, castling, en passant, pawn promotion (with underpromotion), 50-move and insufficient-material draws.
- **Two game modes**: local two-player, and single-player vs. computer — either a fixed ELO you choose (800–2400) or an "Adaptive" opponent that tracks your rating up or down as you play.
- **Ratings dashboard**: your ELO, win/loss/draw record, and last 10 games, all persisted between visits.
- **Chess clock**: Bullet (1+0), Blitz (3+2), Rapid (10+0), Classical (30+0), or no clock — with real increments and time-out detection.
- **PGN**: live move list plus a one-tap "Copy PGN" for pasting into any chess site or database.
- **Three board themes**: Classic Wood, Modern Minimal, Cyberpunk Neon — switch instantly, no reload.
- **Built for touch**: large tap targets, legal-move dots, gold selection ring, board flip, and locked zoom/scroll so it feels native on iPad.

## Host it on GitHub Pages

1. Create a new GitHub repository (public repos get free Pages hosting).
2. Upload all four items above (`index.html`, `manifest.json`, `sw.js`, `icons/`) to the repo root, keeping the `icons` folder structure intact.
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch", pick your default branch (usually `main`) and the `/ (root)` folder, then **Save**.
5. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/` — it usually takes a minute or two the first time.
6. Open that URL — that's the link you'll use on your iPad/Android.

## Install on iPad (Safari)

1. Open your GitHub Pages URL in **Safari** (must be Safari, not Chrome, for the install prompt to appear).
2. Tap the **Share** icon (square with an arrow pointing up).
3. Scroll down and tap **Add to Home Screen**.
4. Tap **Add**. The app icon now appears on your home screen and opens full-screen, with no browser bars.

## Install on Android (Chrome)

1. Open your GitHub Pages URL in **Chrome**.
2. Tap the **⋮** menu in the top right.
3. Tap **Add to Home screen** (or you may see an **Install app** banner/icon in the address bar — tap that instead).
4. Confirm. The app installs like a native app and opens standalone.

## Notes
- Everything — the rules engine, the AI, your stats — runs entirely in the browser. Nothing is sent anywhere.
- The AI's strength is controlled by search depth, calculated randomness, and occasional deliberate mistakes at lower ELO — it's tuned to feel like a genuinely weaker or stronger opponent, not just a slower one.
- Undo is available in Two Player mode only, to keep single-player ratings meaningful.
- If you ever want to reset your rating and history, clearing your browser's site data for the page will do it (there's no in-app reset button by design, to avoid accidental resets).
