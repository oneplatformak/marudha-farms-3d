# Marudha Farms — Interactive 3D Estate

Open-world 3D visualisation of the Marudha Farms agricultural estate & private farmhouse, generated from the owner's hand-drawn site plan.

**Live:** https://oneplatformak.github.io/marudha-farms-3d/

## What you can do
- **Guided tour** — cinematic sunrise opening at the main gate, then 17 hand-framed stops (~100 s). Share a stop with `?stop=farmhouse`, `?stop=swimming-pool` …
- **Walk / Drive** — walk (W A S D, Shift = run) or drive the estate jeep, gates open, enter buildings.
- **Fly / Top view** — orbit the whole master plan.
- **Click any zone** for its description and approximate area.
- **Estate overview** — estate total, zone breakdown, highlights.
- **Master plan** — the illustrated site plan.
- **Time of day** — sunrise to night (stars, glowing farmhouse windows and lamps).
- **Photo / Share / Fullscreen** — save a screenshot, copy the link, present full-screen.
- **Quality presets** — Ultra / High / Medium / Low, auto-picked for the device (`?q=high` to force). **Look** — Bright (default) or Cinematic (grain, vignette, deeper contrast).
- **Ambient sound** — off by default; 🔊 in the tour bar turns on synthesised wind, birdsong and a soft pad.

Works on desktop and mobile (touch joystick).

## Zones
Pine forest · Teak forest · Forest strip · 3 farmland blocks · Central well · Goat farm (shed, pens, paddock) · Labour quarters · Farm office · Farmhouse + pool · Coconut plantation · Car parking · Main & secondary roads · Proposed: solar array, rainwater tank, compost, machinery shed.

## Tech
Single static page: [three.js](https://threejs.org) (r170, vendored) with real PBR textures (Poly Haven CC0, see `CREDITS.md`), a physically-inspired shader sky that also lights reflections, GTAO ambient occlusion, bloom + film grade, planar-reflection pool water, wind sway on foliage, alpha-cutout trees (coconut, teak, pine, mango-type), instanced crops / grass / far forests, terrain with patchwork fields and the distant hills, and static geometry merged at load (~70 draw groups). No build step — open `index.html` or serve the folder. Docs: `docs/status.md`, `docs/upgrade-log.md` (before/after per stop), `docs/handoff.md`.

| File | Purpose |
|---|---|
| `index.html` | the whole app (UI + scene + controls) |
| `estate-data.js` | zones, walls, doors, windows, objects, tour route (metres) |
| `three.module.js`, `OrbitControls.js`, `BufferGeometryUtils.js`, `RoomEnvironment.js`, `postprocessing/`, `shaders/` | three.js runtime (vendored) |
| `masterplan.jpg` | illustrated site plan |

## Accuracy
Conceptual model. Provisional scale: 1 sketch px = 15 cm (≈ 248 m × 170 m estate, ~6.9 acres). Not a survey; orientation unknown. Replace `estate-data.js` with survey-based geometry when available.
