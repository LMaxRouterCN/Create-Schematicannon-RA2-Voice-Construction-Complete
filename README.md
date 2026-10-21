# Create Schematicannon: RA2 Voice - Construction Complete

A Minecraft resource pack that replaces the Create mod's Schematicannon "printing finished" chime with the classic Red Alert 2 EVA voice line: "Construction complete."

## Features

- Replaces `create:schematicannon_finish` (the note block bell) with the RA2 EVA voice line
- Pitch-corrected: Create plays this event at a hardcoded 0.7 pitch (about -6 semitones). The pack compensates with a 1.4286 multiplier, so the voice plays at its natural pitch (residual deviation ~0.02 cent, imperceptible)

## Requirements

- Minecraft 1.20.1
- Create 0.5.1 for 1.20.1

## Install

Folder: copy the `Create-Schematicannon-RA2-Voice-Construction-Complete` folder into your instance's `resourcepacks/` directory.

Zip: compress the contents of that folder (so `pack.mcmeta` sits at the archive root), drop the zip into `resourcepacks/`, then enable it in-game.

Then let a Schematicannon finish printing a schematic, and listen.

## How it works

- `assets/create/sounds.json` overrides the `schematicannon_finish` entry with `replace: true`, pointing to a custom sound in the `ra2` namespace
- The audio file lives at `assets/ra2/sounds/construction_complete.ogg` (Vorbis, mono, 22050 Hz)
- `pitch: 1.4286` on the sound entry cancels out Create's hardcoded 0.7 playback pitch

## Credits and licensing

- Files authored for this pack are licensed under the MPL-2.0 (see LICENSE)
- The voice line and audio are assets of Command & Conquer: Red Alert 2, (c) EA / Westwood Studios. This is a non-commercial fan work for personal use, not affiliated with or endorsed by EA.
