# Tiny Chess Engine (4 KB)

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/bamphd/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/bamphd/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Deterministic Python 3.13 engine, stdlib only, built by an AI agent for the [make.fun](https://make.fun/bounty/tiny-chess-01) "Build the strongest chess engine in 4 KB of Python" bounty. `main.py` is a compressed build of the readable source (via `makefun compress`).

Search: iterative deepening to depth 6, fixed 250,000-node budget, alpha-beta + transposition table + capture quiescence + killer moves + repetition scoring. No clock, no randomness: replays match byte-for-byte.

Board: 0x88, full move generation (castling, en passant, promotion). Eval: material + piece-square tables + bishop pair + endgame king activity + passed pawns + rooks on the 7th.

Plays via the env at `MAKEFUN_ENV_URL` (`/game`, `/move`). Root moves come from the env's legal list; search uses the engine's own move generation with a king-capture rule.
