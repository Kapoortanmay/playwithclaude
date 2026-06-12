# Tic Tac Toe

A polished, single-file Tic Tac Toe game with an AI opponent, persistent leaderboard, and a clean dark interface inspired by Apple's design language and the Claude Code aesthetic.

**[Play it live →](https://kapoortanmay.github.io/tictactoe/)**

---

## Features

| Feature | Details |
|---|---|
| **Two game modes** | Player vs Player · Player vs Claude (AI) |
| **Unbeatable AI** | Minimax algorithm with alpha-beta pruning |
| **Persistent leaderboard** | Scores saved in `localStorage` — survive page reloads |
| **Animated marks** | SVG X and O marks draw themselves on placement |
| **Aurora background** | Three colour-shifting orbs + an interactive particle network |
| **Clawd mascot** | Pixel-art recreation of the Claude Code mascot with idle float and blink animations |
| **Typewriter intro** | Animated tagline on the home screen |
| **Zero dependencies** | Pure HTML · CSS · JavaScript — one file, no build step |

---

## How to Play

### Starting a game
1. Open the page — you land on the **home screen**.
2. Choose a mode with the segmented control:
   - **vs Friend** — two players share the same keyboard/screen.
   - **vs Claude** — you play X, the AI plays O.
3. Enter player name(s) and press **Start Game**.

### Gameplay
- Click any empty cell to place your mark.
- The first player to line up three marks horizontally, vertically, or diagonally wins.
- A tied board is declared a draw.
- After each round, the result is recorded on the leaderboard.

### Leaderboard
- Displays all recorded results with player avatars, win/draw/loss counts, and win rates.
- Use the **Clear** button to reset it.

---

## AI Opponent

The "vs Claude" mode uses **Minimax with alpha-beta pruning** — the AI evaluates every possible future board state and always picks the optimal move. It cannot be beaten; the best result against it is a draw.

Scoring inside the algorithm:
- Win for AI → `+10 − depth` (prefers faster wins)
- Win for human → `−10 + depth` (prefers slower losses)
- Draw → `0`

---

## Tech Stack

- **HTML5** — semantic markup, single `index.html`
- **CSS3** — custom properties, `backdrop-filter` frosted glass, `@keyframes` animations, CSS Grid for the board
- **Vanilla JavaScript** — game logic, minimax AI, canvas particle network, localStorage leaderboard
- **SVG** — animated X/O marks (`stroke-dashoffset` draw-on effect), pixel-art Clawd mascot
- **Web Canvas API** — interactive particle network on the home screen

---

## Running Locally

No installation required.

```bash
# Clone the repo
git clone https://github.com/Kapoortanmay/tictactoe.git

# Open in browser
open tictactoe/index.html
```

Or just download `index.html` and open it directly — it is entirely self-contained.

---

## Project Structure

```
tictactoe/
└── index.html   # Entire game — markup, styles, and logic in one file
```

---

## Design Notes

- **Colour palette** — pure black background (`#000000`), frosted-glass cards (`rgba(14,14,18,0.78)`), terracotta accent (`#D97757`) for the Claude/AI theme, Apple blue (`#0A84FF`) for PvP.
- **Typography** — `-apple-system, BlinkMacSystemFont, "SF Pro Display"` system font stack.
- **Mascot** — 11 × 7 pixel grid at 12 px/cell (SVG `viewBox="0 0 132 84"`), faithfully recreating the Clawd character from Claude Code using `#CC785C`.
- **Particles** — 50 nodes; warm-orange and white types; lines drawn between nodes closer than 150 px; mouse repels nodes within 90 px.

---

## License

MIT — do whatever you like with it.
