# World 02: Balon (Cappadocia-style hot-air balloon operations)

```text
Build a single-file interactive web app (one index.html with inline CSS and JS) using Three.js
r170 loaded as an ES module from https://cdn.jsdelivr.net/npm/three@0.170.0/ (import map, OrbitControls
from examples/jsm). A live 3D hot-air balloon flight operations dashboard called "Balon" for a fictional
Cappadocia-style valley that feels like a strategy game.

WORLD: a low-poly isometric valley built entirely in code, no external models, textures or fonts
beyond one Google Font. Fairy-chimney rock towers with cone caps (instanced, varied heights), soft
eroded ridges in layered beige, pink and ochre bands, a cave hotel carved into a cliff with lit windows
and terraces, a small village with flat roofs and a minaret, vineyards and apricot orchards in
patches, a winding valley road, three launch fields with trucks, trailers and inflation fans, a
landing meadow, a weather mast and a control cabin. 12 balloons with striped envelopes (each its own
colour pair), wicker baskets, burners and passengers. Clean toy-like clay look, soft shadows, one accent
colour (#F97316 burner orange, used for burner flames, UI highlights and the selection ring) on warm
sand and dawn-sky tones.

LIFE: one dawn mission loops forever: crews unload baskets, fans cold-inflate the envelope (it swells
from flat to round), burners fire with a flame flicker and glow, the balloon stands up, passengers
board, it lifts off, drifts with the wind field (a slowly rotating vector field with gusts) through
the valley at different altitudes, dips between rock towers, rises to view height, then descends to the
landing meadow where a chase truck drives to the predicted landing point and the crew deflates and
packs the envelope. Balloons keep separation: each one reserves an altitude band and holds or climbs
when another balloon is within 40 m, so nothing ever overlaps. Chase trucks follow the road, stop for
each other at junctions. Birds circle the cliffs, smoke rises from village chimneys.

INTERACTION: drag to pan, right-drag to rotate, scroll or pinch to zoom (OrbitControls, clamped so the
camera never goes under the ground). Click any balloon, launch field, chase truck, the cave hotel or the
weather mast (raycast against invisible hit boxes): the camera glides to it and follows if it moves, a
pulsing ring and a floating label mark it, and a glass panel shows live stats. An area switcher flies
between Launch fields, Rose valley, Village, Cave hotel and Landing meadow.

DASHBOARD: frosted glass panels over the 3D view: top bar (logo, search for any object, area switcher,
weather menu, live clock starting at 05:40, alerts, day/night toggle), 3 KPI cards (Balloons airborne,
Passengers flying, Wind at 300 m), a right detail panel, a bottom-left flight tracker for the selected
balloon (Cold inflate, Hot inflate, Boarding, Lift-off, Cruise, Landed) and a tabbed live table
(Balloons, Crews, Weather). Realistic, fictional data: balloon call signs like "TC-BAL 07", envelope
volume in m³, altitude in m, burner fuel %, wind in knots. No real company or people's names.

EXTRAS: weather modes (Calm dawn, Gusty wind with flights held on the ground and an alert, Morning mist
pooling in the valleys, Light snow on the rock caps) that change light, fog, materials and particles;
animated day/night from pre-dawn blue to golden sunrise with long shadows, burner glows readable in the
dark; works on mobile with a bottom-sheet panel.

PERFORMANCE (must run at 60 fps on an Intel UHD 620 laptop iGPU): renderer pixel ratio capped at
1.5, antialias on, one directional light with a 1024 shadow map that only covers the play area,
InstancedMesh for every repeated object (rock towers, trees, vines, houses, windows, people), merge
static geometry, MeshLambert/MeshStandard materials only, no post-processing passes, at most ~150 draw
calls (log renderer.info.render.calls to the console every 5 s), particles as one Points object per
effect. Pause the simulation when the tab is hidden. Add a "?low" URL flag that halves particles and
turns shadows off. Add a "?record" URL flag that hides the cursor and UI chrome except the KPI cards and
starts a cinematic camera that glides between the areas.

Deliver only the finished index.html. No build step, no server needed: it must open by
double-clicking the file.
```
