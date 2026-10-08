# Blast Off Builder

A 3D rocket-building game for young kids (around age 5), made for phones and tablets.

- Drag engines, boosters, rocket bodies, noses, fins and wings from the tray onto the launch pad.
- Add pipe junctions to branch out: each pipe arm ends in a glowing socket where a new tower can be built, above the arm or hanging below it. Tap a junction to swing its arms around.
- Tap a part to turn it. Parts often arrive upside down or sideways.
- Pick a pilot (astronaut, cat, dog, robot, alien or bunny) and drop them into a cockpit or cabin.
- Decorate with gadgets (radar dish, blinking lights, headlights, fans, antenna, solar panel) and stickers. They're just for fun.
- Press **GO** and each pilot walks over, rides a lift up beside the rocket, waves and hops into their seat; then comes a spoken countdown. A good rocket blasts off into space, jumps to hyperspeed with the stars streaking past, and lands on its engines on an alien planet, where the locals cheer. Every flight lands on a different planet (candy, aurora ice, lava, jungle, rust, bubblegum or a grey moon with Earth in the sky), each with its own sky, suns, ground, craters, rock spires or arches, floating rocks, glowing plants and a mix of aliens: one-eyed blobs, three-eyed stalk aliens, octopuses, winged bugs, floating jellyfish and tiny flying saucers, and after each flight the next launch starts from a new place: a meadow, a forest clearing, a platform out at sea, a city park, the desert or the snow. A broken one crashes and bursts into flames (the pilots parachute to safety). The OOPS screen shows what was wrong, and after tapping the wrench, markers point at each problem until it's fixed.

A rocket flies when the main tower has an engine at the bottom and a nose on top, noses sit only at the top of a tower, every part is the right way up, it has at least 2 fins, and a pilot is on board. More engines make it fly faster, including engines on branch towers.

## Run it

It's one page plus the sound clips in `assets/`. Serve the folder (for example `python -m http.server 5204`) and open it in a browser; it needs an internet connection for the 3D library and font. No build step. Opened straight from disk it still works, but the browser won't load the clips, so you hear the built-in synthesized sounds and the device's own voice instead.

Built with [three.js](https://threejs.org/).

## Play offline (add to Home Screen)

On iPhone or iPad, open the game in Safari, tap **Share → Add to Home Screen**, then open it once from the new icon while online. After that it starts full screen and works without internet. Changes I publish arrive on their own: the next online launch downloads them and the one after shows them.

(How: `manifest.webmanifest` gives the icon and full-screen mode; `sw.js`, a service worker, keeps a copy of every file the game uses, including three.js, the font and the sound clips.)

## Tuning knobs

At the top of the sound section in `index.html`:

- `CLIP_VOL`: how loud the sound effect clips are (0 to 1).
- `VOICE_VOL`: how loud the spoken lines are (0 to 1).
- `CLIP_TRIM` and `RUMBLE_TRIM`: per-clip volume trims that even out the clips, which ElevenLabs made at different levels. Lower a number if a sound is too loud.
- `ASSET_V`: bump it after replacing any file in `assets/`, so phones don't keep the old one.

## Audio credits

Voices and sounds: [elevenlabs.io](https://elevenlabs.io). All clips were made on 2026-10-08 with an ElevenLabs **free** plan, so they may only be used non-commercially and must credit ElevenLabs. They are not covered by any licence on this game's code.

- **Spoken lines** (`assets/say-*.mp3`, `assets/hint-*.mp3`, 22 clips): voice "Jessica", model Eleven Multilingual v2. Pilot names (Astronaut, Captain Cat, Doggo, Robot, Alien, Bunny), "All aboard!", the "Three, Two, One, Blast off!" countdown, "Hyperspeed!", "A new planet!", "Wheee!", and the eight OOPS hints ("It needs an engine at the bottom!" and so on).
- **Sound effects** (`assets/sfx-*.mp3`, 16 clips): ElevenLabs Sound Effects. Pop, poof, gentle "nope", giggle, parachute, landing thump, lift-off whoosh, slide-whistle swoop, warp charge, warp jump, warp arrival, engine sputter, cartoon crash, victory fanfare, sad trombone, and the looping engine rumble.

The tiny UI blips (pick, turn, boop, countdown beeps) are still synthesized in the browser.
