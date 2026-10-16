# World 01: Vapur (Bosphorus ferry operations)

```text
Build a single-file interactive web app (one index.html with inline CSS and JS) using Three.js
r170 loaded as an ES module from https://cdn.jsdelivr.net/npm/three@0.170.0/ (import map, OrbitControls
from examples/jsm). A live 3D ferry operations dashboard called "Vapur" for a fictional Istanbul-style
strait that feels like a strategy game.

WORLD: a low-poly isometric strait built entirely in code, no external models, textures or fonts
beyond one Google Font. Two shores (Europe and Asia) with hills of colourful stacked houses, a long
suspension bridge with two towers and cables, three ferry piers with clock-tower terminal buildings,
a lighthouse on a tiny island, a hilltop mosque silhouette with domes and two minarets, a stone
tower on a hill, a coastal road with cars, simit carts and tea gardens on the quays, plus white-red
city ferries with funnels, a car ferry, fishing boats, a tanker passing through the middle of the
strait and seagulls. Animated water with gentle waves and a lighter current lane in the middle.
Clean toy-like clay look, soft shadows, one accent colour (#E30A17 Turkish red, used on ferry funnels,
UI highlights and the selection ring) on warm off-white and sea teal.

LIFE: ferries run a timetable between the three piers forever: dock, lower the gangway, passengers
(small instanced figures) walk off and on, raise the gangway, sound a horn (a small expanding ring),
depart along a curved route and cross the strait. The car ferry shuttles across loading cars.
The tanker sails slowly along the middle lane; ferries give way to it and wait at a hold point,
so nothing ever overlaps. Fishing boats bob near the shore, cars drive the coastal road and stop
at a pedestrian crossing, seagulls circle and follow the ferries' wake.

INTERACTION: drag to pan, right-drag to rotate, scroll or pinch to zoom (OrbitControls, clamped so
the camera never goes under the water). Click any ferry, pier, the tanker, the bridge or a tea garden
(raycast against invisible hit boxes): the camera glides to it and follows if it moves, a pulsing
ring and a floating label mark it, and a glass panel shows live stats. An area switcher flies between
Northern pier, Bridge, Central pier, Southern pier and Island lighthouse.

DASHBOARD: frosted glass panels over the 3D view: top bar (logo, search for any object, area switcher,
weather menu, live clock, alerts, day/night toggle), 3 KPI cards (Passengers this hour, On-time
departures %, Ferries in service), a right detail panel, a bottom-left voyage tracker for the selected
ferry (Docked, Boarding, Departed, Crossing, Arriving, Docked) and a tabbed live table (Ferries, Piers,
Strait traffic). Realistic, fictional data: ferry names like "Kalamış" or "Martı 3", passenger counts,
speed in knots, departure times. No real people's names.

EXTRAS: weather modes (Sunny, Poyraz wind with choppy waves and rocking boats, Lodos storm with rain,
lightning and ferries cancelled, Morning fog with fog horns and low visibility) that change light,
fog, materials and particles; animated day/night where the bridge lights cycle through colours,
house windows glow and the lighthouse beam sweeps; works on mobile with a bottom-sheet panel.

PERFORMANCE (must run at 60 fps on an Intel UHD 620 laptop iGPU): renderer pixel ratio capped at
1.5, antialias on, one directional light with a 1024 shadow map that only covers the play area,
InstancedMesh for every repeated object (houses, windows, trees, people, cars, gulls), merge static
geometry, MeshLambert/MeshStandard materials only, no post-processing passes, at most ~150 draw calls
(log renderer.info.render.calls to the console every 5 s), particles as one Points object per
effect. Pause the simulation when the tab is hidden. Add a "?low" URL flag that halves particles
and turns shadows off. Add a "?record" URL flag that hides the cursor and UI chrome except the KPI
cards and starts a cinematic camera that glides between the areas.

Deliver only the finished index.html. No build step, no server needed: it must open by
double-clicking the file.
```
