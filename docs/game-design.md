# Pixel Adventure - Game Design Document

## Concept

A classic 2D pixel-art platformer inspired by retro games. The player navigates through levels filled with enemies, obstacles, and power-ups, trying to reach the exit door at the end of each level.

## Visual Style

- **Chunky pixel art** - all graphics drawn as large visible pixels (5x scale)
- **Procedural sprites** - no image files, everything generated in code
- **Animated backgrounds** - 3-layer parallax forest with twinkling stars and moon
- **Character animations** - 3-frame walk cycles with leg movement

## Characters

### Cat
- Orange tabby with pink inner ears
- Green eyes with dark pupils
- Whiskers extending from face
- Lighter belly fur and tail

### Dog
- Brown body with darker floppy ears
- Red collar around neck
- Pink tongue showing
- Lighter belly area

### Wolf
- Grey body with darker ear tips
- Yellow eyes with amber pupils
- Lighter snout and jaw area
- Fur tufts on sides, belly highlights

## Level Design Philosophy

### Level 1: Dark Forest (Easy)
- Teaches basic movement and jumping
- Simple water pit with platforms above
- Introduction to lava (short gap)
- First encounter with slimes and bats
- Gentle elevation changes

### Level 2: Lava Caves (Medium)
- Underground setting with ceiling
- Multiple lava pits requiring platform hopping
- Brick pillar obstacles with openings
- Spike traps on the ground
- More enemies in tighter spaces

### Level 3: Sky Islands (Hard)
- No ground - floating platforms over water
- Requires precise jumping between small platforms
- Varying heights demanding careful timing
- Many bats in open air
- Brick towers as obstacles

## Enemy Behavior

### Slime
- Patrols horizontally between defined boundaries
- Turns around when hitting walls or patrol limits
- Affected by gravity (falls off edges)
- Defeated by stomping from above
- Visual: bouncing animation (squish/stretch)

### Bat
- Flies in sine-wave pattern horizontally
- Turns at patrol boundaries
- Avoids flying through solid tiles
- Defeated by stomping or fireballs
- Visual: wing flap animation

## Power-Up System

Items spawn from special blocks when hit from below. Each block gives a different item (cycling through 4 types).

### Fire Flower (10 seconds)
- Shoot up to 3 bouncing fireballs
- Fireballs bounce on ground, destroyed on walls
- Kill enemies on contact
- Orange glow around player

### Speed Star (8 seconds)
- 60% faster movement speed
- Click for instant speed burst
- Yellow glow around player

### Shield (15 seconds)
- Absorbs one hit (enemy or hazard)
- Click for area slam attack (kills nearby enemies)
- Blue bubble visual around player
- Consumed on hit

### Super Jump (7 seconds)
- 50% higher normal jumps
- Click for instant mega-jump (works in air)
- Purple glow around player

## Scoring

| Action | Points |
|---|---|
| Collect coin | +50 |
| Defeat enemy (stomp) | +100 |
| Defeat enemy (fireball) | +100 |
| Collect power-up | +200 |
| Complete level | +500 |

## Lives System

- 3 lives per level
- Lives reset when entering any level
- Death respawns at level start (same level)
- Game over = respawn same level with 3 new lives
- No permanent game over / no going back to earlier levels

## Controls

- **Movement**: WASD or Arrow keys
- **Jump**: Space, W, or Up arrow
- **Double Jump**: Press jump again while airborne (slightly weaker)
- **Crouch**: Hold Shift (hitbox shrinks, slower movement)
- **Use Power**: Left mouse click or F key

## Future Ideas

- More enemy types (flying enemies, boss enemies)
- Moving platforms
- Underwater sections
- Character-specific abilities
- Level editor
- Sound effects and music
- High score persistence (localStorage)
- More levels
- Secret areas and hidden items
