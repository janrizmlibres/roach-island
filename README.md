# Roach Island

An endless side-scroller in LÖVE where you take out as many roaches as you can before they take you out. They're the same size as you. It was my final project for Harvard's CS50x in 2020.

## Running it

You need [LÖVE](https://love2d.org/) 11 or later. From the repository root:

```bash
love .
```

## Controls

| Key | Action |
|---|---|
| A and D | Move |
| W | Jump |
| J | Shoot |
| Space | Turn around, which also flips the direction you shoot |
| Enter | Start from the main menu |
| Escape | Back to the menu, or quit from the menu |

Press Space on the main menu for the instructions.

## How to play

The screen scrolls on its own, so keep moving. You have 3 lives and each roach hit costs one. Falling into a gap or getting left behind by the screen ends the run on the spot.

Roaches don't chase you. They wander, idling or running in a random direction, and spawn on any ground the map generates, sometimes right where you land. Each one takes 3 hits. Shooting knocks it back, and jumping on its head bounces you off it, which helps you cross a crowd. Knocking a roach off the island counts as a kill too.

Every 20 kills the scrolling speeds up. Your best score is saved between runs.

## How it works

`Map.lua` builds the island out of random strips of land, 4 to 20 tiles wide at random heights, with gaps between them, and drops roaches on random floor tiles. Once a screen's width has scrolled past, the map shifts its right half to the left and generates a fresh right half, so the island never ends. The player and roaches live in `actors/`, and `main.lua` runs the menu, play and game over screens.

## License

MIT. See [LICENSE](LICENSE).
