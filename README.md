# NEJS

A small platformer written in plain JavaScript on a canvas, at the NES resolution of 256×240. Sprites are 16×16 tiles cut from one tileset image, and levels are placed on a tile grid. The physics and collisions are written by hand. There is no build step and no dependencies.

You can play it at https://nejs-five.vercel.app.

## The game

The level has a few brick platforms, a stone pillar, a question block and two enemies. One enemy patrols the upper right platform and the other starts on the ground to the right of the pillar. Enemies walk back and forth and turn around when they hit a wall or the edge of the screen.

Jump on an enemy to defeat it and bounce off its head. Touch one from the side and the page reloads, which restarts the level.

## Controls

| Key | Action |
| --- | --- |
| `A` `D` | move |
| `W` or `Space` | jump |
| `Shift` | run |
| `Enter` | pause and resume |
| `R` | restart |

## Running

The page loads ES modules from absolute paths, so serve the repository root over HTTP:

```bash
npx serve .
```

## Code

| File | Role |
| --- | --- |
| `src/scripts/main.js` | game loop and keyboard input |
| `src/scripts/world.js` | the scene: player, enemies and walls |
| `src/scripts/render.js` | canvas setup and the per-frame update and draw |
| `src/scripts/sprites.js` | loads `public/assets/testTiles.png` and slices it into sprites |
| `src/scripts/classes/Entity.js` | movement, gravity and the collision checks shared by everything |
| `src/scripts/classes/Player.js`, `Enemy.js`, `Wall.js` | the three kinds of object in the scene |

## Other branches

The [`previous-main`](https://github.com/gabreusi/NEJS/tree/previous-main) branch holds a later state of the project. It scales the canvas to 768×720 and adds a sprite editor, a debug panel, hitbox display and sub-areas for collisions. It was left in a buggy state, so `main` went back to this November 2023 version, where the enemies and collisions work.
