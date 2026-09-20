# NEJS

An experiment in drawing a platformer the way an NES does, in plain JavaScript on a canvas. There is no build step and no dependencies.

The canvas is 768×720, three times the NES resolution of 256×240. Graphics are built from 8×8 tiles with four-color palettes and grouped into metatiles. The brick, ground and Goomba sprites are pixel arrays in `src/scripts/sprites`. The player accelerates up to a walking or running speed cap and can jump only while on the ground. Entities carry hitboxes that can be drawn on screen.

The scene in `main.js` is a hardcoded test level with a player and two platforms.

## Running

The page loads ES modules from absolute paths, so serve the repository root over HTTP:

```bash
npx serve .
```

## Controls

| Key | Action |
| --- | --- |
| `A` `D` | move |
| `W` or `Space` | jump |
| `Shift` | run |
| `Enter` | pause and resume |
| `.` | advance one frame while paused |
| `R` | reload |

The "Debug" button toggles the debug panel, and "Sprite Edit" opens an 8×8 pixel editor with the color palette.
