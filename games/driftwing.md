# DRIFTWING

**[▶ Play DRIFTWING](https://amusehall.com/games/driftwing/?utm_source=github&utm_medium=game-file&utm_campaign=awesome-games-made-with-ai)** · [Original post](https://github.com/KyleBuildsAI/driftwing)

<a href="https://amusehall.com/games/driftwing/?utm_source=github&amp;utm_medium=game-file&amp;utm_campaign=awesome-games-made-with-ai"><img src="https://media.amusehall.com/driftwing/preview.webp?v=3102edce40" alt="DRIFTWING by @KyleBuildsAI" width="100%"></a>

- **Made with:** Claude Opus 5.5, Claude Code
- **Creator:** [@KyleBuildsAI](https://github.com/KyleBuildsAI)
- **Genre:** Flight, Exploration
- **Plays on:** Computer and phone
- **Price:** Free
- **Controls:** Mouse or arrow keys to steer, W and S for throttle, 1-6 to switch aircraft, C to change view; an on-screen stick on phones
- **Likes on the original post:** Unknown

A calm, endless flight over procedural snow peaks, deserts and island chains, with six aircraft and a talking copilot called WREN.

## Play notes

You fly over a world that is generated as you go, from snowy peaks and pine valleys to deserts and flower meadows, with no fuel, no enemies and no way to lose. Keys 1 to 6 swap between a glider, a bush plane, a jet, a helicopter, a wingsuit and an FPV drone, and C cycles chase, wing and cockpit views, with working gauges in the cockpit. A copilot named WREN points out sights such as floating islands and, when you type or speak to it, sets waypoints, flies for you or changes the time of day; a world map and a journal track what you find. The page opens on the newer version, the first one-prompt build is a toggle away, and the creator shared that first prompt. Works on phones and computers.

## Prompt

```text
Build a complete, self-contained browser game in a SINGLE index.html file. No build step, no external assets, libraries only via CDN importmap. Use three.js (latest) with WebGPURenderer and automatic WebGL fallback.
THE GAME: "DRIFTWING", an ambient infinite-flight exploration game. You pilot a low-poly glider over an endless procedural world. No fail state, no fuel, no enemies. The fantasy: a golden-hour flight that never has to end, with an AI copilot riding shotgun.
FLIGHT MODEL (arcade with soul):
- Mouse steers pitch and roll (WASD/arrows also work), scroll or W/S for throttle, space for a gentle boost on cooldown
- Banking turns: rolling into a turn induces natural yaw; speed bleeds in climbs and builds in dives
- Soft stall: below minimum speed the nose eases down, never a tumble
- Chase cam with smooth lag that banks with the plane, FOV stretches with speed, subtle shake at max velocity
- Touch support: virtual joystick plus throttle slider
- Double-tap A or D triggers a smooth canned barrel roll
INFINITE TERRAIN (the engineering core):
- Chunked heightmap terrain from seeded simplex noise, multiple octaves, fully deterministic from a seed shown in the UI so worlds are shareable
- Biomes blended by temperature/moisture noise: snow peaks, pine valleys, dunes, archipelago ocean, flower meadows; vertex-colored, flat-shaded low-poly
- Chunk generation in a Web Worker with transferable buffers, ring LOD (high detail near, low far), pooled and recycled chunk meshes, zero frame hitches while streaming
- Stitched LOD edges or skirts so there are never visible cracks
- Procedural landmarks every few km: stone arches, monolith circles, a lighthouse on a lone island, drifting hot air balloons; discoveries log to a journal
LIVING ATMOSPHERE:
- Day/night cycle (6 min loop, settable): sun, moon, star field, dawn/dusk gradients, aurora over snow biomes at night
- Sky: gradient dome with a sun disc and cheap radial god rays near the horizon; fog color always matches the sky
- Clouds: instanced soft puffs in a slow-drifting layer casting faint shadow blobs
- Water: animated vertex waves, sun glint streak, foam band at shorelines
- Boid bird flocks that scatter when you dive through them
- Wingtip contrails when banking hard, wind streak lines at speed
THE COPILOT (critical architecture):
- class Copilot { async respond(flightState, transcript) -> { speech, action } }
- Default brain = local keyword grammar via the Web Speech API: "where am I", "find mountains / ocean / desert", "set waypoint", "autopilot on/off", "make it night / dawn", "barrel roll", "ring course"
- Executable actions: place a glowing waypoint beacon, autopilot to a heading, change time of day, spawn a ring course, describe current biome and altitude
- RemoteCopilot: POSTs { flightState, transcript } to a configurable endpoint (default http://localhost:3000/copilot), expects { speech, action } back, falls back to the local grammar after an 800ms timeout
- Copilot answers via speechSynthesis plus a subtitle line in the glass UI; mic toggle with a pulsing listening indicator; every command also reachable by keyboard/UI so voice is never required
GENTLE OBJECTIVES (optional, never nagging):
- Ring courses on request: fly-through rings with chime feedback, time and best streak
- Discovery journal: biomes visited, landmarks found, distance flown, max altitude
- Photo mode: P pauses, frees the camera, hides UI, adds letterbox and a screenshot button
VISUAL QUALITY BAR (this is the entire point):
- Cohesive 6-color palette per biome, flat shading, soft sun shadows
- Post stack: subtle bloom, vignette, warm color grade, light film grain
- Golden-hour default start: long shadows, warm fog, the screenshot moment inside the first 5 seconds
- Minimal glass UI: altitude, speed, compass strip, waypoint arrow, world seed, mic toggle; auto-hides after 3 seconds of stillness
PERFORMANCE:
- 60fps target on desktop: frustum culling, instancing for trees/rocks/clouds, worker-side terrain, auto-degrade view distance before frame drops
- Guard against: LOD cracks, falling through unloaded chunks (clamp altitude to terrain height plus epsilon), NaN attitude, worker backlog, tab-blur dt spikes
POLISH RULES:
- Every listed system must actually function, zero placeholders
- Opens already airborne at golden hour with a 1-second fade, no menu wall, no console errors
```

This is part of the prompt; the creator didn't share all of it.

[Where the creator shared it](https://github.com/KyleBuildsAI/driftwing#about-this-project)

<sub>The game and its prompt belong to @KyleBuildsAI. Preview recorded by us. [Ask for a change or removal](https://github.com/evorjh/awesome-games-made-with-ai/issues/new?template=change-or-removal.yml).</sub>
