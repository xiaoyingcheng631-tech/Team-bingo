# Team Bingo – Classroom Territory Battle

A fully self-contained, single-file interactive web game for classroom group competitions.

- One teacher operates it on a laptop, projected onto a classroom screen.
- 3 teams (default Red / Blue / Green — names and colors customizable) battle over **one shared 3×3 keyword board per round**.
- **Multiple Bingo pages / game rounds**: prepare 3, 5, 10 or more rounds before class via 🗂 Bingo Pages — each with its own title, board size, keywords, question list, board ownership and scores. Switch instantly with Prev / Next Round or the page dropdown; one round's data is never touched by another.
- **Fully customizable board size per round**: rows and columns can each be set from 2 to 20 (max 400 squares, e.g. 2×2, 3×3, 4×5, 6×8, 10×10, 20×20). Change the size in each page's ✎ editor — winning lines (full rows / full columns / diagonals on square boards) adapt automatically, and a confirmation dialog protects existing keywords and claimed squares before any change is applied.
- Students answer questions; correct answers let the teacher claim a square in the team's color.
- Automatic Bingo detection (rows / columns / diagonals, per round), live scoreboard, question display & navigation, square ownership editing, Big Board projector mode.
- Question navigation and the Bingo board are fully independent — switching questions never resets territory; switching rounds restores each round's own progress.
- All Bingo pages and their progress (teams, colors, scores, claimed squares, current question per round) are saved in the browser's localStorage and restored after a page refresh. Older single-round saves are migrated automatically. **🔄 Reset Game** offers both "Reset This Round" and "Reset ALL Rounds".

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire application — HTML, CSS and JavaScript in one file. No dependencies, no build step, no backend. |

## Run Locally (optional)

Double-click `index.html` to open it in any modern browser — no server or installation required.

## Deploy to a Public HTTPS URL

Because the site is 100% static, any static host works. Pick one:

### Option 1 — Netlify Drop (easiest, no account setup needed to try)
1. Go to https://app.netlify.com/drop
2. Drag the folder containing `index.html` onto the page.
3. You instantly get a public HTTPS URL (e.g. `https://random-name.netlify.app`). Sign in to keep the link permanent and rename the site.

### Option 2 — Vercel
1. Install the CLI once: `npm i -g vercel`
2. In this folder run: `vercel` (first time: accept the defaults)
3. Run `vercel --prod` to publish. Your URL looks like `https://team-bingo-site.vercel.app`.
   No `vercel.json` is needed — a static `index.html` is detected automatically.

### Option 3 — GitHub Pages
1. Create a repository (e.g. `team-bingo`) and push these files:
   ```
   git init
   git add index.html README.md
   git commit -m "Team Bingo website"
   git branch -M main
   git remote add origin https://github.com/<your-user>/team-bingo.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Source: Deploy from a branch → main / (root) → Save**.
3. Your site goes live at `https://<your-user>.github.io/team-bingo/` (usually within 1–2 minutes).

## Publishing Future Updates

The application is a single file, so updating the live site means re-uploading one file:

- **Netlify Drop:** drag the updated folder onto the drop page again (same account keeps the same URL), or use the Netlify dashboard → Deploys → drag & drop.
- **Vercel:** edit `index.html`, then run `vercel --prod` from this folder again. The URL stays the same.
- **GitHub Pages:** edit `index.html`, commit, and push:
  ```
  git add index.html
  git commit -m "Update game"
  git push
  ```
  GitHub Pages redeploys automatically.

## Cross-Device Compatibility

Works in any modern browser (Chrome, Edge, Safari, Firefox) on Windows, macOS, iPads/tablets, and iPhones/Android phones. No installation, no login, no registration. The layout is responsive; the teacher should operate from a laptop for the best experience.

## Notes

- State is stored per-browser: each device keeps its own game session (the classroom teacher's laptop holds the authoritative game).
- To reset everything, use the **🔄 Reset Game** button (clears squares and scores, keeps keywords/questions/team settings) or clear the site's browser data.
