# Marudha Farms — Interactive 3D Estate

Open-world 3D visualisation of the Marudha Farms agricultural estate & private farmhouse, generated from the owner's hand-drawn site plan.

**Live:** https://oneplatformak.github.io/marudha-farms-3d/

## What you can do
- **Guided tour** — cinematic dawn opening at the main gate, then every zone (letterbox, soft music).
- **Walk / Drive** — walk (W A S D, Shift = run) or drive the estate jeep, gates open, enter buildings.
- **Fly / Top view** — orbit the whole master plan.
- **Click any zone** for its description and approximate area.
- **Estate overview** — estate total, zone breakdown, highlights.
- **Master plan** — the illustrated site plan.
- **Time of day** — sunrise to night (stars, glowing farmhouse windows and lamps).
- **Photo / Share / Fullscreen** — save a screenshot, copy the link, present full-screen.
- **High quality toggle** — bloom glow + shadows (desktop) or performance mode (mobile).
- **Ambient sound** — optional synthesised wind and birdsong.

Works on desktop and mobile (touch joystick).

## Zones
Pine forest · Teak forest · Forest strip · 3 farmland blocks · Central well · Goat farm (shed, pens, paddock) · Labour quarters · Farm office · Farmhouse + pool · Coconut plantation · Car parking · Main & secondary roads · Proposed: solar array, rainwater tank, compost, machinery shed.

## Tech
Single static page: [three.js](https://threejs.org) (r170) with procedural textures (grass, soil, stone, brick, tile, wood, water), alpha-cutout foliage (palm fronds, tree canopies, crops, grass tufts), instanced vegetation, merged static geometry (~200 draw calls), bloom post-processing, dynamic sun/night cycle. No build step — open `index.html` or serve the folder.

| File | Purpose |
|---|---|
| `index.html` | the whole app (UI + scene + controls) |
| `estate-data.js` | zones, walls, doors, windows, objects, tour route (metres) |
| `three.module.js`, `OrbitControls.js`, `BufferGeometryUtils.js`, `RoomEnvironment.js`, `postprocessing/`, `shaders/` | three.js runtime (vendored) |
| `masterplan.jpg` | illustrated site plan |

## Accuracy
Conceptual model. Provisional scale: 1 sketch px = 15 cm (≈ 248 m × 170 m estate, ~6.9 acres). Not a survey; orientation unknown. Replace `estate-data.js` with survey-based geometry when available.
