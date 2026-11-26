# Handoff note for the next AI session

Read `docs/status.md` and `docs/upgrade-log.md` first.

- Single-file app: `index.html` (module script). Data: `estate-data.js` (`window.ESTATE`). Do not change zone polygons/areas — they drive the Estate overview numbers.
- Tour stops live in `ESTATE.route[]`: `p:[x,z]`, `h` (camera height), `look:[x,y,z]`, `fov`, `text`. Caption switches at 45 % of each leg (`tourUpdate`).
- Rendering pipeline: RenderPass → GTAOPass (half-res on High) → UnrealBloom → OutputPass → film grade ShaderPass. Quality presets in `QUAL` / `setQuality()`. Look toggle in `setLook()`.
- Static geometry is baked at load into ~72 merged meshes grouped by material signature (colour → vertex colours). Anything that must stay dynamic needs `userData.skipBake` (e.g. the pool `Water`).
- Terrain: `heightAt()` analytic + `terrainY()` bilinear from the generated mesh — always place objects with `terrainY`.
- Textures: `tex/<set>/{d,n,r}.webp` from Poly Haven (CC0), listed in `CREDITS.md`; loaded through a `LoadingManager` that drives the loader bar.
- Debug hooks in the console: `window.__dbg` (tour, gotoStop, setMode, setQuality, gtao, bloom, camera), `window.__renderer`, `window.heightAt`.
- Verification routine used so far: load the live page, `window.__dbg.tour.playing=false; window.__dbg.gotoStop(i)`, screenshot, compare with `docs/after/stop-XX.jpg`.
- Commit SHAs: Phase 0 `d503f11`/`be2a31d`, Phase 2 textures `80014a8`, Phase 0.5 `01fa102`…`23fbcf0`, Phase 0.6 `48a82ba`, UX/SEO `d54657b`.
