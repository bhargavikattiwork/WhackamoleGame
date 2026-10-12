# Mole Patrol

A quick, single-player Whack-a-Mole arcade game built as a standalone HTML file. The goal is to hit the active mole as fast as possible before the 30-second round ends.

## Overview

Mole Patrol is a browser game designed to be:

- playable immediately with no installation
- responsive on desktop and mobile screens
- easy to understand for casual players
- compatible with mouse, touch, and keyboard input
- self-contained with no external dependencies or network access required

The game lives in a single file: [whack-a-mole.html](whack-a-mole.html). The product requirements and acceptance criteria are documented in [PRD_whack_a_mole.md](PRD_whack_a_mole.md).

## How to Play

1. Open [whack-a-mole.html](whack-a-mole.html) in any modern browser.
2. Click the Start game button to begin a 30-second round.
3. Watch for the mole that pops up from one of the nine holes.
4. Click or tap the matching hole to score a point.
5. Avoid missing the mole or clicking an empty hole, since both count as misses.
6. The round ends when the timer reaches zero.
7. Your best score is saved in browser local storage on the same device.

## Controls

- Mouse or touch: click/tap the active hole
- Keyboard: press keys 1 through 9 to hit the corresponding hole
- Pause/Resume: use the in-game pause control
- Sound: toggle sound effects on or off

## Gameplay Features

- 3x3 game board with one active mole at a time
- 30-second round timer
- score, misses, and best score tracking
- increasing speed as the player scores more points
- pause and resume support
- restart support
- optional sound effects
- responsive layout for smaller screens
- browser local storage for persistent best score

## Project Structure

- [whack-a-mole.html](whack-a-mole.html) — complete game markup, styling, and JavaScript
- [PRD_whack_a_mole.md](PRD_whack_a_mole.md) — product requirements and acceptance criteria
- [README.md](README.md) — project overview and usage guide

## Running the Game

No build step or package install is required.

### Option 1: Open directly in a browser

- Double-click [whack-a-mole.html](whack-a-mole.html), or
- open it via your browser's File > Open menu

### Option 2: Serve locally

If you prefer a local web server, you can run a simple static server from the project folder, then open the page in a browser.

Example:

```bash
python -m http.server 8000
```

Then visit:

```text
http://localhost:8000/whack-a-mole.html
```

## Notes

- The game is intentionally self-contained and does not rely on external assets or libraries.
- Audio is optional and automatically disabled gracefully if browser audio support is unavailable.
- Best score persistence uses browser storage, and the game continues to work even if storage is unavailable.

## License

This project does not currently include a formal license file. If you intend to share or distribute it publicly, you may want to add an appropriate open-source license before release.
