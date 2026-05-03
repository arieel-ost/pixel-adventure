# Pixel Adventure - Project Instructions

## Overview

Single-file pixel-art platformer game (`index.html`). Everything is in one HTML file: styles, sprites, levels, physics, rendering.

## Architecture

- **No frameworks** - pure vanilla JS + Canvas 2D
- **No image assets** - all sprites are procedurally drawn as 2D color arrays
- **Single file** - entire game in `index.html` for simplicity
- **Tile-based** - 8x8 pixel tiles, rendered at 5x screen scale (PX=5)
- **Game resolution** - 160x120 game pixels = 800x600 screen pixels

## Key Systems

### Rendering
- `drawPx(x, y, color)` - draw one game pixel
- `drawSprite(x, y, sprite)` - draw 2D color array
- `drawTile(tx, ty, type, camX, camY)` - draw tile with procedural texture
- Camera follows player with smooth lerp

### Physics
- Tile-based collision (`checkTileCollision`)
- Gravity, variable jump height
- Double jump (one extra jump in air)
- Crouch (shrinks hitbox from 12 to 7 pixels)

### Characters
- `makeCatFrame(legFrame)`, `makeDogFrame(legFrame)`, `makeWolfFrame(legFrame)`
- 3 walk animation frames each
- Horizontal flip for left-facing

### Enemies
- Slimes: ground patrol with wall collision and gravity
- Bats: flying patrol with sine-wave movement, wall-aware
- Both die when stomped from above or hit by fireball

### Items / Power-ups
- `TILE.MUSHROOM_BLOCK` (type 9) - hit from below to spawn items
- 4 item types cycle: fire, speed, shield, superjump
- Items have physics (gravity, wall bounce)
- Powers are timed, shown in HUD

### Levels
- `createLevel1()`, `createLevel2()`, `createLevel3()` - return level objects
- Each has: tiles[][], enemies[], coins[], spawn, exit, bg settings
- 3 lives per level, respawn in same level on game over

## Game States

`menu` -> `playing` -> `dead` / `levelcomplete` -> `gamecomplete`

## Tile Types

0=Air, 1=Ground, 2=Grass, 3=Stone, 4=Brick, 5=Spike, 6=Water, 7=Lava, 8=Platform, 9=ItemBlock

## Adding Content

### New Level
1. Create `createLevelN()` following existing pattern
2. Add to `LEVELS` array
3. Include enemies, coins, item blocks, spawn, exit

### New Enemy Type
1. Create sprite function `makeXFrame(frame)`
2. Add movement logic in the enemy update loop
3. Add collision handling

### New Power-Up
1. Add sprite function and entry in `ITEM_SPRITES`
2. Add to `ITEM_TYPES` array
3. Handle in `usePower()` for mouse click
4. Handle in update loop for passive effects
5. Add HUD label in `drawHUD`

## Conventions

- All coordinates in game pixels (not screen pixels)
- Tile coords: multiply by 8 to get pixel coords
- Sprites: null = transparent, string = color
- Enemy `vx` can be negative (moving left) or positive (right)
- Level bg settings are ignored (unified forest background for all levels)
