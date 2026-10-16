# Living world prompt template

Six blocks, always in this order. Blocks 1-5 follow the structure popularised by the free
"World Prompt Pack" by @sanjai.builds (World, Life, Interaction, Dashboard, Extras). Block 6 is ours:
it keeps the result smooth on an Intel UHD iGPU with 8 GB RAM.

Fill the `<...>` parts. Keep everything else as is.

```text
Build a single-file interactive web app (one index.html with inline CSS and JS) using Three.js
r170 loaded as an ES module from https://cdn.jsdelivr.net/npm/three@0.170.0/ (import map, OrbitControls
from examples/jsm). A live 3D <WHAT IT RUNS> dashboard called "<NAME>" that feels like a strategy game.

WORLD: a low-poly isometric <PLACE> built entirely in code, no external models, textures or fonts
beyond one Google Font. <8-12 LANDMARKS, BUILDINGS AND VEHICLES>. Clean toy-like clay look,
soft shadows, one accent colour (<HEX>) on <BACKGROUND>.

LIFE: <THE MAIN LOOP, STEP BY STEP>. <OTHER THINGS THAT MOVE>. Every mover follows a path
(CatmullRom curves or lane graphs) with a simple reservation system: it waits when the next segment
is taken, so nothing ever overlaps. Loops forever.

INTERACTION: drag to pan, right-drag to rotate, scroll or pinch to zoom (OrbitControls, clamped so
the camera never goes under the ground). Click any <OBJECTS> (raycast against invisible hit boxes):
the camera glides to it and follows if it moves, a pulsing ring and a floating label mark it, and a
glass panel shows live stats. An area switcher flies between <4-5 AREAS>.

DASHBOARD: frosted glass panels over the 3D view: top bar (logo, search for any object, area switcher,
weather menu, live clock, alerts, day/night toggle), 3 KPI cards (<KPI 1>, <KPI 2>, <KPI 3>), a right
detail panel, a bottom-left <PROCESS> tracker (<6 STEPS>) and a tabbed live table (<3 TABS>).
Realistic, fictional data: <UNITS>. No lorem ipsum, no real people's names.

EXTRAS: weather modes (<4 MODES>) that change light, fog, materials and particles; animated
day/night with glowing windows and lights; works on mobile with a bottom-sheet panel.

PERFORMANCE (must run at 60 fps on an Intel UHD 620 laptop iGPU): renderer pixel ratio capped at
1.5, antialias on, one directional light with a 1024 shadow map that only covers the play area,
InstancedMesh for every repeated object (trees, people, cars, windows), merge static geometry,
MeshLambert/MeshStandard materials only, no post-processing passes, at most ~150 draw calls
(log renderer.info.render.calls to the console every 5 s), particles as one Points object per
effect. Pause the simulation when the tab is hidden. Add a "?low" URL flag that halves particles
and turns shadows off.

Deliver only the finished index.html. No build step, no server needed: it must open by
double-clicking the file.
```

## Follow-ups that help

- "Add a cinematic mode: the camera glides slowly between the most interesting areas." (Good for videos.)
- "Some movers still overlap at junctions. Fix the give-way logic so they queue instead."
- "Check renderer.info: cut draw calls below 100 with instancing and merged geometry."
- "Add a ?record URL flag: hide the cursor, start cinematic mode, fix the clock to 18:30." (For screen capture.)
