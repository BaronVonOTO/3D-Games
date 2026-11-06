# Dusk Dunes

A browser-based 3D world with ten themed worlds, over thirty short games, live-generated music, positional sound, real stereoscopic 3D viewing modes, and peer-to-peer multiplayer. It is one self-contained HTML file with no build step, no accounts and no downloads, and it runs on desktop and on phones.

## Play

Open `index.html` in a modern browser (or host the folder on any static web server) and click **Start**.

| | Desktop | iPhone / touch |
|---|---|---|
| Look | Mouse (click to capture) | Tilt or turn the phone, or swipe |
| Move | `W A S D` or arrow keys, `Shift` to run | Always moving forward |
| Brake | n/a | Touch and hold |
| Jump | `Space` | Tap, or flick the phone up |
| Dive / swim down / fly down | `C` | Flick the phone down |
| Fly up (Zen Wander) | Hold `Space` | Tilt the phone up |
| Pause menu | `Esc` | **Menu** button |
| Change 3D view | `M` | Pause menu |

The pause menu is where you pick the world, the game, the 3D view, effects and multiplayer. Hover (or tap) a game card to read a one-line description, and use the search box and category filter (multiplayer, single player, or a genre) to find a game quickly.

## Worlds

Each world changes the scenery, sky, lighting, music scale, footstep sound and how you move.

| World | What is different |
|---|---|
| Dusk Dunes | Downhill slopes speed you up; shooting stars |
| Coral Reef | Swim up and down (`Space` / `C`); bubbles and floating pickups |
| Moon Base | Low gravity for long leaps; Earth in the sky |
| Candy Kingdom | Speed pads give a short sugar rush |
| Haunted Moor | Lightning flashes light up the fog |
| Neon Grid | Flat synthwave plain; glowing lanes boost your speed |
| Cloud Peaks | Huge mountains; ride updraft columns |
| Ember Caverns | Lava pools slow you down; rising embers |
| Frozen Aurora | Icy ground: you slide and keep momentum; snow and aurora |
| Mushroom Jungle | Glowing mushrooms bounce you high |

## Games

- **Open world:** Treasure Island, Escape the Forest, Lost Explorer, Delivery Driver, Zombie Escape, Mountain Climber, Alien Planet, Bank Robbery Escape, Island Survival, Mystery Village
- **Multiplayer:** Hide & Seek, Obstacle Race, King of the Hill, Treasure Rush, Rising Lava, Hot Tag, Team Defense, Hot Potato, Light Rush
- **Classic modes:** Light Hunt, Hot & Cold, Statues, Capture the Flag, Safe Zone, Meteor Dodge, Memory Lights, Stop and Go, Snake Trail, Demolition, Herding, Beacon Defense, Zen Wander

**Zen Wander** has no goals: fly freely (hold `Space`), float along a lazy river, swim in the ponds and wade the streams.

On-screen text is kept to what matters for play: direction arrows, villager messages, warnings and countdowns. A setting restores the full timers and counters.

## 3D viewing

Pick one **3D view** and stack any number of **effects** on top of it.

- **Views:** normal, red/cyan and optimized red/cyan anaglyph, parallel and cross-eyed side by side, Cardboard phone-headset view (with lens distortion), ChromaDepth, depth map, disparity map, random-dot and pattern autostereograms, sway parallax, double-image overlay, wipe compare.
- **Effects:** invert colors, fisheye dome, kaleidoscope, underwater ripple, tilt-shift miniature, chromatic split, toon outline, contour lines, neon depth edges, night vision, 8-bit dither, CRT scanlines.
- Side-by-side views (parallel, cross-eyed and Cardboard) crop each eye to half the screen instead of squashing the picture, so nothing is stretched. The Cardboard lens distortion is aspect-correct.
- In 3D views the on-screen text is drawn into both eyes at its natural proportions so it stays readable and fuses at a comfortable depth. The text size slider scales it.
- Depth strength can be adjusted and the eyes swapped in Settings.

Both eyes are rendered from the actual scene, so no depth estimation is involved.

## Water

Ponds, lakes and streams are carved into the terrain, so the water has real depth. You wade in the shallows and swim in deep water (slower, head at the surface; hold `C` to dive, with blue fog underwater). Streams and the lazy river carry you along with their current. Sliders in Settings set how many ponds and streams appear, and the multiplayer host's values are shared with everyone so all players see the same water. Trees, buildings and obelisks are never placed in water, and pickups float on the surface. Games that build their own arena (for example the obstacle race) skip the extra water.

## Sound

Everything is synthesized live with the Web Audio API; there are no audio files.

- **Music:** stereo, generated from the world (scale, tempo, instruments) and the game (calm, explore, mystery, tense, action or party mood).
- **Positional sound:** zombies growl, police sirens sweep past, boulders rumble, meteors whistle, sheep bleat, lights chime, and other players' footsteps are heard from where they actually are, using HRTF 3D audio. Headphones work best.
- **Effects:** pickups, jumps, landings, hits, splashes and swimming strokes, win or lose jingles, plus quiet stereo footsteps that change with each world's ground. Streams burble in 3D as you pass them.
- Music and sound effects have independent volume sliders. On iPhone the ring/silent switch can mute web audio.

## Multiplayer

Peer-to-peer over WebRTC using [PeerJS](https://peerjs.com). One player chooses **Host** and shares the four-letter code; others enter it and choose **Join**.

- The host runs the shared game state, so everyone sees the same objects, scores and results. Players appear as named avatars, bump into each other, and can be heard in 3D.
- The right to choose the next world and game rotates between players every round.
- Modes with real interaction include tag, bomb passing, contested hills, stealing treasure, a rising-lava race and hide and seek with a blind seeker.
- Matchmaking uses the free public PeerJS broker. Strict corporate networks may need a TURN server.

## Settings

Music and sound-effect volume, text size, phone mode, 3D depth, swap eyes, text in both eyes, full HUD text, and population sliders for **trees**, **buildings**, **obelisks**, **ponds and lakes** and **flowing streams**.

## Install on a phone or desktop

- **iPhone:** in Safari choose Share, then Add to Home Screen. It opens full screen with the dusk icon.
- **Desktop:** the page ships with a rounded favicon and a web app manifest, so Chromium browsers offer to install it.

## Hosting

The repository root is the whole site. Any static host works. A GitHub Pages workflow is included (`.github/workflows/pages.yml`): set Pages to use GitHub Actions and push to `main`. Motion sensors (iPhone tilt) and the clipboard-free features need HTTPS, which Pages provides.

## Built with

- [three.js](https://threejs.org) r128 for rendering
- Web Audio API for music, effects and positional sound
- [PeerJS](https://peerjs.com) for multiplayer
- Plain HTML, CSS and JavaScript in a single file

## Browser support

Current Chrome, Edge, Firefox and Safari (desktop and iOS 14.5+ for device tilt). WebGL is required. Wake Lock keeps the screen on during play where the browser supports it (iOS 16.4+).

## Project layout

```
index.html              the entire game
manifest.webmanifest    install metadata
icon-180.png            Apple touch icon (square)
icon-192.png, icon-512.png   rounded install icons
.github/workflows/      GitHub Pages deployment
```
