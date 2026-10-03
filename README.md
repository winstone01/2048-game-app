# Winstone's 2048 Game

A browser-based 2048 game built with **HTML, CSS and vanilla JavaScript**. Slide numbered tiles around a 4 × 4 board, combine matching values and aim to create a **2048 tile**.

**[Play the live game](https://winstone01.github.io/2048-game-app/)**

## Features

- A 4 × 4 board generated dynamically with JavaScript.
- Arrow-key controls for moving tiles in four directions.
- Matching-tile merging and a running score.
- Two starting tiles, each with a value of 2.
- Randomly positioned new 2 tiles during play.
- Tile colours that change with their numeric values.
- Win detection when a tile reaches 2048.
- Game-over detection that checks for both empty spaces and available neighbouring matches.
- A soft gradient background, rounded tiles and a separate score display.

## How to Play

| Key | Action |
| --- | --- |
| Arrow Up | Move tiles upwards |
| Arrow Down | Move tiles downwards |
| Arrow Left | Move tiles left |
| Arrow Right | Move tiles right |

Combine equal tiles to build larger numbers: **2 → 4 → 8 → 16 → … → 2048**. Each merge adds the resulting tile value to the score. The score is separate from the value of your largest tile.

A full board can still have legal moves. The game ends when there are no empty cells and no equal tiles next to each other horizontally or vertically.

The current game uses a keyboard. Refresh the page to start a new game; scores and board state are not saved between sessions.

## Technologies

| Technology | Role |
| --- | --- |
| HTML5 | Page structure and score display |
| CSS3 | Board layout, typography and visual styling |
| JavaScript | Board creation, movement, merging, scoring and game-state checks |
| Google Fonts | Source Sans 3 font |
| GitHub Pages | Static website hosting |

No framework, package installation, backend or build step is required. Google Fonts needs an internet connection to load; the stylesheet includes a sans-serif fallback.

## Project Files

| File | Purpose |
| --- | --- |
| `index.html` | Game page and board container |
| `style.css` | Layout and appearance |
| `script.js` | Game logic and tile colours |
| `README.md` | Documentation |

## Run Locally

1. Download or clone the repository:

   ```bash
   git clone https://github.com/winstone01/2048-game-app.git
   cd 2048-game-app
   ```

2. Open `index.html` in a browser, or serve the folder with VS Code's Live Server extension.
3. Use the arrow keys to play.

Keep `index.html`, `style.css` and `script.js` together so the relative file paths work.

## How the Code Works

JavaScript creates 16 tile elements and stores them in the `squares` array. Their displayed numbers represent the board state.

Movement functions extract rows or columns, remove zero values and add empty spaces on the appropriate side. Merge functions combine matching values, update the score and compress the tiles again before generating a new tile.

`checkForWin()` looks for a 2048 tile. `checkForGameOver()` first checks for zeros, then checks matching neighbours to the right and below while respecting the board boundaries. Tile backgrounds are updated by `addColours()`.

## Current Limitations and Next Steps

The published version is a learning project with a few remaining edge cases:

- Row merging needs a boundary guard so the last cell of one row cannot merge with the first cell of the next.
- Tile generation currently runs after every arrow-key action. It should run only after a board change and handle a full board without retrying recursively.
- The winning branch of `checkForWin()` needs to return `true` so callers can recognise the win.
- The fixed-width board and keyboard-only controls could be extended with a responsive layout and touch controls.

Other possible additions include a New Game button, saved best score and move animations.

## Learning Focus

This project practises DOM manipulation, array filtering, row and column indexing, keyboard events, random tile placement and game-state logic. The loss check demonstrates why a full board and an unplayable board are different conditions.

## Author

**Winstone Anderson** — UI-focused front-end developer.

- [GitHub](https://github.com/winstone01)
- [Portfolio](https://winstoneanderson.com)

