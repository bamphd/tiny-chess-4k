# Tiny Chess Engine (4 KB)

Deterministic Python 3.13 engine, stdlib only. `main.py` is a
compressed build of the readable source (via `makefun compress`).

Search: iterative deepening to depth 5, fixed 50,000-node budget,
alpha-beta + transposition table + capture quiescence. No clock,
no randomness: replays match byte-for-byte.

Board: 0x88, full move generation (castling, en passant,
promotion). Eval: material + piece-square tables + bishop pair.

Plays via the env at `MAKEFUN_ENV_URL` (`/game`, `/move`).
Root moves come from the env's legal list; search uses the
engine's own move generation with a king-capture rule.
