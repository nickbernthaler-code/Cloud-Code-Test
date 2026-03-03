# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Project Overview

A single-file Tic Tac Toe game. There is no build system, package manager, or external dependencies.

## Running / Development

Open `tictactoe.html` directly in a browser — no build step or server required.

To verify changes work correctly, open the file in a browser and confirm:
- Clicking cells places X and O alternately
- Winning combinations are highlighted with a pulse animation
- The scoreboard updates after each game
- The Restart button resets the board without clearing scores

## Architecture

Everything lives in `tictactoe.html` — HTML structure, embedded `<style>`, and an inline `<script>` block.

### Key game logic (in the `<script>` block)

| Symbol | Purpose |
|--------|---------|
| `board` | `Array(9)` tracking `'X'`, `'O'`, or `null` for each cell |
| `current` | Active player (`'X'` or `'O'`) |
| `over` | Boolean; blocks clicks once the game ends |
| `scores` | `{ X, O, D }` object persisted across restarts |
| `WINS` | Constant array of the 8 winning index triples |
| `init()` | Resets board/DOM for a new game (scores survive) |
| `checkWin()` | Iterates `WINS`; returns winning triple or `null` |
| `handleClick()` | Click handler: updates `board`, DOM, checks win/draw |
| `updateScores()` | Syncs `scores` object to scoreboard DOM elements |

## Rules for AI

- The user is a beginner coder. Explain your reasoning briefly when you make choices.
- Always add comments to code you write, explaining what each section does.
- Before making changes, briefly describe what you plan to do.
- Prefer simple solutions over clever ones.
- If you are unsure what the user wants, ask a clarifying question before writing code.
