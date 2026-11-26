# Project status — Marudha Farms 3D

**Live:** https://oneplatformak.github.io/marudha-farms-3d/  ·  **Repo:** `oneplatformak/marudha-farms-3d` (public; GitHub Pages from `main`, root)

## What it is
A single-page three.js (r170, vendored) 3D walkthrough of the Marudha Farms master plan. `estate-data.js` is the single source of truth (zones, walls, doors, windows, items, buildings, palms, tour route with hand-tuned cameras). `index.html` builds everything procedurally from it at load.

## Current state (27 Nov 2026)
- Phases 0, 0.5, 0.6 done and verified on the live build (see `docs/upgrade-log.md`).
- Quality presets Ultra/High/Medium/Low (auto-picked, `?q=` override), Bright/Cinematic look toggle, day/night slider, GTAO, bloom, film grade, reflective pool, PBR textures (CC0), deep links `?stop=<slug>`, screenshot, share link.
- Desktop High: 86–96 FPS on a MacBook. Mobile: untested on a real device.

## Known gaps / next
1. Phase 1 real GLTF models — blocked here (asset sizes / sources). Option: author models procedurally in a node script and export GLB (GLTFExporter + gltf-transform/Draco) so loaders/LOD/instancing can be exercised.
2. Farmhouse interior walk-through, animated workers, engine sound.
3. CSM shadows, height fog, weather toggle.
4. Mobile verification on a real phone (375 px layout, 30 FPS at Medium).
5. Lighthouse run.

## How to build
`gen/world` (outside this repo, on the authoring machine) holds `app_head.html + scene_block.js + app_tail.js` → `python3 build.py` concatenates them into `index.html` (adds a build stamp for cache-busting). If you only have this repo, edit `index.html` directly — it is plain HTML/JS, no bundler.
