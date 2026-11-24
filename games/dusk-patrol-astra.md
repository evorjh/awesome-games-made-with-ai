# Dusk Patrol — Autumn Lake District

**[▶ Play Dusk Patrol — Autumn Lake District](https://amusehall.com/games/dusk-patrol-astra/?utm_source=github&utm_medium=game-file&utm_campaign=awesome-games-made-with-ai)** · [Original post](https://x.com/Densitylucky/status/2122834417647513702)

<a href="https://amusehall.com/games/dusk-patrol-astra/?utm_source=github&amp;utm_medium=game-file&amp;utm_campaign=awesome-games-made-with-ai"><img src="https://media.amusehall.com/dusk-patrol-astra/preview.webp?v=d85f8e7cdd" alt="Dusk Patrol — Autumn Lake District by @Densitylucky" width="100%"></a>

- **Made with:** GPT-6.2 Astra
- **Where they name the AI:** [“同一套提示词，Claude Fable 5.2 vs GPT-6.2 Astra 实测：各做一款像素风飞行游戏。”](https://x.com/Densitylucky/status/2122834417647513702)
- **Creator:** [@Densitylucky](https://x.com/Densitylucky)
- **Genre:** Flight, Sandbox
- **Plays on:** Computer
- **Price:** Free
- **Controls:** Mouse to steer, click to roll, hold to boost, right mouse button or F to fire, Space to cycle views
- **Likes on the original post:** 869, counted 2026-11-24

Pilot a pixel-art jet above autumn lakes, switch into its instrument-filled cockpit and fire missiles into the landscape.

[Play notes →](https://amusehall.com/games/dusk-patrol-astra/?utm_source=github&utm_medium=game-file&utm_campaign=awesome-games-made-with-ai)

[How the creator made it →](https://amusehall.com/games/dusk-patrol-astra/?utm_source=github&utm_medium=game-file&utm_campaign=awesome-games-made-with-ai#making-of)

## Prompt

```text
Build "Patrol": a pixel-art fighter-jet flying toy that runs in the browser as one self-contained HTML file. No libraries and no image assets: raw WebGL2 for the world, Canvas 2D for the cockpit, everything drawn by code. Google Fonts are the only external resource (a pixel display face for the title, a monospace face for hints). This should feel like a polished indie game demo, not a tech test, so spend your effort on how it looks and how it feels to fly.

LOOK
- Render at a low internal resolution (about 340 px tall) and upscale with nearest-neighbour so pixels stay crisp. Limited palette, ordered 4x4 Bayer dithering between tones, no anti-aliasing, no smooth gradients.
- Setting: lake country in autumn at the last light of day. Warm low sun, violet shadows, peach clouds, haze toward the horizon that is gold toward the sun and lilac away from it.

WORLD
- Generate a seamlessly tiling height field at load (use web workers and show a progress bar), then ray-march it per pixel in a fragment shader so any camera angle works.
- Water: depth bands from pale turquoise shallows to navy, animated foam along shores, short white glints, sky reflection at low angles and a glitter path under the sun.
- Land: sand, pale meadows, forest in patches of orange, crimson and gold with scattered dark conifers, grey-violet rock, snow on the highest peaks, subtle terraced shading, long baked shadows.
- A layer of puffy cumulus below cruise altitude, shaded in stepped tones, casting shadows on the ground. Sky gradient with a large sun disc and thin high streaks.

AIRCRAFT
- An original twin-engine, twin-tail fighter: pointed dark radome, gold-tinted bubble canopy, cropped delta wings, canted fins with red caps, glowing nozzles, grey and slate splinter camouflage. Low-poly mesh, flat-shaded in three tones, with a one-pixel dark outline.
- Thin white vapour trails from the wingtips, twin afterburner plumes with a white core, the jet's shadow on ground and clouds, spray and a wake when skimming water.

CAMERAS AND CONTROLS
- Three views cycled with Space, blending smoothly over about a second: top-down (north up), chase, and cockpit.
- Mouse steers. In the top view the jet flies toward the cursor; in chase and cockpit the cursor's offset from centre sets turn and climb or dive. Click: barrel roll. Hold: afterburner. Right click or F: fire a missile. Left and right buttons must work together.
- Arcade flight: it cannot crash, it pulls up on its own before terrain, and it flies lazy S-turns until the player first moves the mouse. Add touch controls with on-screen buttons.

COCKPIT
- A hand-plotted pixel instrument panel where every reading is real: airspeed, artificial horizon, altimeter with digits, turn and slip, heading, vertical speed, an amber ground-mapping radar with a sweep, engine gauges, a clock showing local time, warning lamps, a throttle lever that follows the afterburner.
- A head-up display whose pitch ladder sits exactly on the real horizon outside, with heading tape, speed, altitude, G, radar height, missile count and warnings.

MISSILES
- Four on the wings; each leaves its rail when fired and re-arms after a few seconds. They fly with a flame and a smoke trail to where the nose points, or to the ground ahead when flying level.
- Impact: flash, fireball, lingering smoke and an expanding shock ring; a scorch with embers on land, a column of spray and foam on water.

INTERFACE
- All text in English: a title card, one quiet strip of control hints with a missile counter, and a sound toggle. Sound is synthesised with Web Audio and off by default.

QUALITY BAR
- Smooth on an integrated GPU; drop internal resolution automatically if frames get slow.
- Before you call it done, run it in a headless browser, screenshot all three views plus a missile strike, and fix whatever looks wrong. Simulate several minutes of random flying and input to confirm there are no errors.
```

[Where the creator shared it](https://x.com/Densitylucky/status/2122836528473002360)

<sub>The game and its prompt belong to @Densitylucky. Preview recorded by us. [Ask for a change or removal](https://github.com/evorjh/awesome-games-made-with-ai/issues/new?template=change-or-removal.yml).</sub>
