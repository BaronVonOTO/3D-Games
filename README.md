# Dusk Dunes

A first-person 3D world in the browser (three.js) with 15 simple game modes and 15 stereoscopic viewing methods
inspired by [Anaglyph & Friends](https://github.com/udeudeude/Anaglyph-and-Friends).

**Controls:** click to look, WASD or arrows to move, Shift to run, Esc to pause (game and view pickers live there),
M cycles views, [ and ] change depth, R restarts the game.

**10 worlds:** Dusk Dunes, Coral Reef, Moon Base, Candy Kingdom, Haunted Moor, Neon Grid, Cloud Peaks, Ember Caverns, Frozen Aurora, Mushroom Jungle. Each world re-themes the scenery and the
15 games (for example Pearl Hunt, Shark Chase, Asteroid Dodge, Gumdrop Delivery, Wisp Hunt).

**32 games** (hover a card in the pause menu for a short description). Open-world: Treasure Island, Escape the Forest, Lost Explorer, Delivery Driver, Zombie Escape, Mountain Climber, Alien Planet, Bank Robbery Escape, Island Survival, Mystery Village. Multiplayer: Hide & Seek, Obstacle Race, King of the Hill, Treasure Rush, Rising Lava, Hot Tag, Team Defense, Hot Potato, Light Rush. Classic modes: Light Hunt, Hot & Cold, Statues, Capture the Flag, Safe Zone, Meteor Dodge, Memory Lights, Stop and Go, Snake Trail, Demolition, Herding, Beacon Defense, Zen Wander.

**3D views** (pick one): normal, red/cyan and optimized red/cyan anaglyph, parallel, cross-eyed, Cardboard phone viewer, ChromaDepth, depth map, disparity map, random-dot and pattern autostereograms, sway parallax, double-image overlay, wipe compare.

**Effects** (checkboxes, stack with any 3D view and with each other): fisheye dome, kaleidoscope, underwater ripple, tilt-shift miniature, chromatic split, toon outline, contour lines, neon depth edges, night vision, retro 8-bit dither, CRT scanlines. Any future non-3D effect goes here too.

**Each world plays differently:** Dusk Dunes (downhill slopes speed you up, shooting stars), Coral Reef (swim with
Space/C, rising bubbles, floating pearls), Moon Base (low gravity leaps, Earth in the sky), Candy Kingdom (sugar-rush
speed pads), Haunted Moor (lightning flashes, drifting wisps).

**New genres:** Pop-Up (whack-a-mole), Memory Lights (Simon), Stop and Go (red light, green light), Gaze Gallery (aim shooter),
Photo Safari, Snake Trail, Dot Eater (maze), Demolition, Herding, Tag, Rally, Beacon Defense, Statues (horror), Gift Catch.

## iPhone / phone mode
On iPhone (or any touch device, or by ticking Phone mode) you always move forward. Turn your body or tilt the phone to
look and steer, touch and hold to brake, tap to jump. Tap Start and allow motion access when asked. Pair it with the
Cardboard view in a headset. (Motion sensors need https, which GitHub Pages provides.)

**New worlds, each with its own mechanic:** Neon Grid (flat synthwave plain, run on glowing lanes for speed), Cloud Peaks
(huge mountains, ride updraft columns), Ember Caverns (lava pools slow you, rising embers), Frozen Aurora (icy sliding,
aurora and snowfall), Mushroom Jungle (bounce on glowing mushrooms). Terrain height now changes per world.

## iPhone extras
Phone mode defaults on for touch devices, and swiping always steers. Flick the phone up to jump and down to dive. The screen is kept awake
(Wake Lock, with a video fallback for older iOS). Safari cannot hide its bars on iPhone, so for true full screen use
Share, Add to Home Screen, and launch it from the home screen.

## Music
Generated live with Web Audio in stereo (panned pads and arpeggios, ping-pong echo, reverb). The world sets the scale, sound and tempo; the game sets the mood (calm, explore, mystery, tense, action, party). A short win or lose jingle plays when a round ends. Use the Music box and volume slider in the pause menu. On iPhone the ring/silent switch can mute it.

## Sound, settings and extras
Music and sound effects each have a volume slider in the Settings dropdown (pause menu). Settings also holds phone mode, 3D depth, swap eyes and the option to draw HUD text into both eyes in 3D views (side-by-side, Cardboard, anaglyph and the rest). Trees and buildings appear in the games where they fit, and always in Zen Wander. Other players' names float over them in multiplayer. The home screen icon is included (icon-180/192/512.png, manifest.webmanifest, plus an inline copy in index.html).

## Multiplayer
Open the pause screen (Esc). One player presses **Host game** and shares the 4-letter code. Others type it and press
**Join**. The chooser rotates every round: the host picks first, then each player in turn picks the next world and game
(the pause menu opens automatically when it is your turn). Everyone gets the same layout (shared seed), sees each
other's avatars, and the top-right scoreboard shows who has finished. The host's R restarts everyone for a rematch.

It uses PeerJS (WebRTC peer-to-peer) with the free PeerJS cloud broker for matchmaking, so it works from GitHub Pages
but not from sandboxed previews that block outside connections. Strict networks may need a TURN server.

## Publish on GitHub Pages
1. Create a new public repo on github.com and upload these files (keep the `.github` folder).
2. Repo Settings, Pages, Source: **GitHub Actions**.
3. Push to `main`. The site appears at `https://YOUR-USER.github.io/YOUR-REPO/`.

No build step. It is a single `index.html` that loads three.js from a CDN.
