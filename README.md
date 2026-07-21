# Browser Games

Two self-contained first-person 3D games. Single HTML file each, Three.js r128 from CDN, zero assets — all geometry, textures and audio are generated procedurally at runtime. Open the file in a browser and play.

## HOLLOW SIGNAL — `horror.html`

First-person horror in a procedurally generated maze.

- Collect 5 pages, then escape through the green door
- Flashlight with battery drain + battery pickups; light helps you see but lets the entity see you from 3x farther
- Phasmophobia-inspired hunt cycles: the entity roams, then periodically hunts. It tracks your **last known position** — sprint away (it's slower than you) or go dark, stand still and let it lose you
- Sprint drains stamina, and emptying it leaves you **out of breath** (audible gasp) — locked to a walk until it recovers past a third. Don't burn it all before a hunt starts
- Sanity system: drains in darkness and near the entity; low sanity = more frequent hunts, whispers, unsteady camera. Recovers slowly in a safe zone (flashlight on, entity far, no active hunt) — rewards careful play, but costs battery so it's never a free reset. The bar tints green while recovering.
- Procedural audio: drone, heartbeat by proximity, growls, breathing radar, distant screams, knocking, jumpscare. Growls, the entity's footsteps and the breathing radar are stereo-panned to its bearing — you can hear which side it's on
- The flashlight's proximity and hunt flicker run on a fixed ~14Hz clock, so the strobe looks the same on a 60Hz and a 144Hz display

> **Difficulty note:** the entity can now actually catch you. Proximity was measured in 3D against a camera sitting 1.65m above an entity standing on the floor, so the grab distance could never fall below 1.65 — while the kill threshold was 1.55. The game was unloseable. Distances are now measured on the floor plane and the grab is re-tested after the entity moves.

Controls: WASD · SHIFT sprint · F flashlight · mouse look · ESC pause

## CORDITE — `shooter.html`

Wave-based arena FPS.

- Hitscan rifle: spread bloom, recoil, reload, tracers, muzzle flash, headshots deal 3x
- Aim down sights (hold RMB): tighter spread, zoomed FOV and steadier look for ranged precision — at the cost of movement speed; sprinting cancels it
- Enemy frames steer around cover, strafe, fire dodgeable projectiles, melee up close; drop health/ammo
- Platforming: jumpable crates, staircases and sniper decks — enemies can't climb
- Escalating waves, score, screen shake, damage feedback, synthesized audio
- Low-integrity warning: a pulsing red vignette and a slow thump kick in below 35% HP so you feel the danger without checking the bar
- Between waves a live countdown shows when the next wave drops; enemy shots flash a muzzle spark at the firing frame so you can read where fire is coming from
- Melee contact now refreshes the integrity bar and plays a throttled hurt cue — previously the bar sat frozen and the damage was silent, so being clawed down read as a bug

Controls: WASD · mouse aim · hold LMB fire · RMB aim down sights · R reload · SHIFT sprint · SPACE jump

Sprint works with either Shift key in both games.

## Roadmap

Larger ideas deferred to keep each change incremental and reversible:

- In-game settings menu (mouse sensitivity, master volume) shared by both games
- Mobile / touch controls (virtual stick + look drag)
- Object pooling for shooter particles, projectiles and tracers (currently per-spawn `new Mesh`)

---

Built with Claude. No build step, no dependencies beyond the Three.js CDN script.
