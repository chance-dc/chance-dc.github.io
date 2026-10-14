# Dylan's Adventure Games

Plain static site (HTML/CSS, no build step) hosted on GitHub Pages at https://chance-dc.github.io.
The site title "Dylan's Adventure Games" lives in `index.html` and each game page header; change freely.

## Layout
- `index.html` – home page with the games grid
- `assets/style.css` – shared styles (fonts: Press Start 2P + VT323 from Google Fonts)
- `games/<slug>/index.html` – game page (iframe player, about, controls, screenshots)
- `games/<slug>/play/` – the AGS web build (contents of the project's `Compiled/Web` folder)
- `.nojekyll` – tells Pages to serve files as-is

## Adding a new game
1. In AGS: General Settings > Build target platforms, tick **Web**; then Build > Build EXE.
2. Copy `games/locked-out/` to `games/<new-slug>/`, edit its `index.html` text and screenshots (`thumb.png`, etc., 640x400 looks good).
3. Replace everything in `games/<new-slug>/play/` with the contents of `<project>/Compiled/Web/` (keep `index.html` at the top of `play/`).
4. Add a card to the grid in the root `index.html`.
5. Optional Windows download: zip `Compiled/Windows`, put it at `games/<slug>/<slug>-windows.zip` (or attach it to a GitHub Release) and point the Download button at it.
6. Test locally: `python3 -m http.server` in the repo root, open http://localhost:8000. Then commit and push; Pages updates in a minute or so.
