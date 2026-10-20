# canli-dunyalar

Single-file Three.js "living world" pages. Each world: `worlds/<name>/index.html` + `shots/`, prompt in `prompts/<name>.md`.

- Three.js pinned to three@0.170.0 via import map (jsdelivr). No build step, no other network deps except one Google Font.
- Performance: pixel ratio ≤ 1.5, one 1024 shadow map, InstancedMesh for repeats, ≤150 draw calls, `?low` and `?record` flags.
- Verify: serve with `python -m http.server 8765 --directory worlds/<name>`, open in the browser, zero console errors, click-select works, night + one weather mode work.
- Code and UI in English; proper names may be Turkish.

## New world
1. Write the prompt in `prompts/<name>.md` using the six blocks of `prompts/template.md` (World, Life, Interaction, Dashboard, Extras, Performance).
2. Build `worlds/<name>/index.html`, then save 1-3 screenshots to `worlds/<name>/shots/`.
3. Add a row to the README table with a `play` link (`https://furkiozknn.github.io/canli-dunyalar/worlds/<name>/`).

## Publishing
- GitHub Pages serves the `master` branch root (classic Pages, no workflow). Every push or merge to `master` goes live at https://furkiozknn.github.io/canli-dunyalar/ within a few minutes, so verify locally first.
- The repo is public: no local paths, test accounts or keys in committed files. Machine-specific notes go in `CLAUDE.local.md` (gitignored).
