# canli-dunyalar

Single-file Three.js "living world" pages. Each world: `worlds/<name>/index.html` + `shots/`, prompt in `prompts/<name>.md`.

- Three.js pinned to three@0.170.0 via import map (jsdelivr). No build step, no other network deps except one Google Font.
- Performance: pixel ratio ≤ 1.5, one 1024 shadow map, InstancedMesh for repeats, ≤150 draw calls, `?low` and `?record` flags.
- Verify: serve with `python -m http.server 8765 --directory worlds/<name>`, open in the browser, zero console errors, click-select works, night + one weather mode work.
- Code and UI in English; proper names may be Turkish.
