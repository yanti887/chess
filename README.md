# Tiny Chess — strongest chess engine in 4 KB of Python

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/yanti887/chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/yanti887/chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original alpha-beta chess engine in at most 4,096 bytes of Python (standard
library only). `main.py` is a packed entrypoint (LZMA stub, written by
`makefun compress` from the readable `engine.py`); it plays the house gauntlet
through the env at `MAKEFUN_ENV_URL`, one game after another, and exits when
every game is over.

## Engine

- 0x88 board, legal move generation (castling, en passant, promotion).
- Alpha-beta search with iterative deepening to a fixed node budget (40,000
  nodes a move — never a clock, so the replay matches), transposition table,
  MVV-LVA + killer + history move ordering, and quiescence over captures.
- Evaluation: material + piece-square tables + bishop pair.
- Deterministic: every move derives from the position, the game's moves and
  the trial seed only.

## Run it

`python3 -P -s main.py` with `MAKEFUN_ENV_URL` set to the env. It reads no
other file and calls no model.

---

Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards
