# Browser Games

Two self-contained first-person 3D games. Single HTML file each, Three.js r128 from CDN, zero assets — all geometry, textures and audio are generated procedurally at runtime. Open the file in a browser and play.

## HOLLOW SIGNAL — `horror.html`

First-person horror in a procedurally generated maze.

- Collect 5 pages, then escape through the green door
- Flashlight with battery drain + battery pickups; light helps you see but lets the entity see you from 3x farther
- Phasmophobia-inspired hunt cycles: the entity roams, then periodically hunts. It tracks your **last known position** — sprint away (it's slower than you) or go dark, stand still and let it lose you
- Sanity system: drains in darkness and near the entity; low sanity = more frequent hunts, whispers, unsteady camera
- Procedural audio: drone, heartbeat by proximity, growls, breathing radar, distant screams, knocking, jumpscare

Controls: WASD · SHIFT sprint · F flashlight · mouse look · ESC pause

## CORDITE — `shooter.html`

Wave-based arena FPS.

- Hitscan rifle: spread bloom, recoil, reload, tracers, muzzle flash, headshots deal 3x
- Enemy frames steer around cover, strafe, fire dodgeable projectiles, melee up close; drop health/ammo
- Platforming: jumpable crates, staircases and sniper decks — enemies can't climb
- Escalating waves, score, screen shake, damage feedback, synthesized audio

Controls: WASD · mouse aim · hold LMB fire · R reload · SHIFT sprint · SPACE jump

---

Built with Claude. No build step, no dependencies beyond the Three.js CDN script.
