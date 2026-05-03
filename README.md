# Pixel Adventure

A retro pixel-art platformer game built with vanilla JavaScript and HTML5 Canvas.

## Play

**[Play Online](https://pixel-adventure.vercel.app)** (link active after deployment)

Or run locally:

```bash
pnpm install
pnpm dev
```

## Characters

Choose from 3 playable characters, each with unique pixel-art designs and walk animations:

- **Cat** - Orange tabby with whiskers, green eyes, and a tail
- **Dog** - Brown pup with floppy ears, a red collar, and a tongue
- **Wolf** - Grey wolf with fur tufts, yellow eyes, and a lighter snout

## Controls

| Action | Keys |
|---|---|
| Move | Arrow keys / WASD |
| Jump | Space / W / Up |
| Double Jump | Press jump again in mid-air |
| Crouch | Hold Shift (shrink to fit under blocks) |
| Use Power | Left mouse click or F key |

## Levels

1. **Dark Forest** - Learn the basics, water pits, lava gaps, brick walls
2. **Lava Caves** - Underground caverns with lava pits and spike traps
3. **Sky Islands** - Floating platforms above water, precision jumping

## Power-Ups

Hit the glowing item blocks from below to release power-ups:

| Item | Effect | Duration |
|---|---|---|
| Fire Flower | Shoot bouncing fireballs (click/F) | 10 seconds |
| Speed Star | Move 60% faster, click for speed burst | 8 seconds |
| Shield | Absorb one hit, click for slam attack | 15 seconds |
| Super Jump | Jump 50% higher, click for mega launch | 7 seconds |

## Enemies

- **Slimes** - Green blobs that patrol the ground. Jump on them!
- **Bats** - Purple flyers that swoop through the air. Jump on them or use fireballs!

## Game Mechanics

- 3 lives per level, reset on each new level
- Collect coins for points (+50 each)
- Defeat enemies by stomping (+100) or fireballs (+100)
- Game over respawns you in the same level with fresh lives
- Parallax forest background with moon and twinkling stars

## Tech Stack

- Vanilla JavaScript (no frameworks for game logic)
- HTML5 Canvas for rendering
- All pixel art drawn procedurally (no image assets)
- Vite for development and building
- Deployed on Vercel

## Development

```bash
pnpm install    # install dependencies
pnpm dev        # start dev server with hot reload
pnpm build      # production build to dist/
pnpm preview    # preview production build
```

## License

MIT
