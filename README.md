# tiny-chess-01-v5

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/axzss/tiny-chess-01-v5/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/axzss/tiny-chess-01-v5/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB chess engine in Python: alpha-beta with iterative deepening, quiescence search, transposition table, killer/history move ordering, null move, LMR, PVS, check extension, aspiration windows, and a tapered piece-square evaluation with tempo, passed-pawn, pawn-structure (doubled/isolated), rook-on-open-file and king pawn-shield bonuses. Built from scratch for the make.fun tiny-chess-01 bounty.

v5 over v3: king pawn-shield safety (-12 per missing shield pawn, phase-tapered), aspiration windows (pv +/-40, depth >= 4, re-search on fail low/high), micro-optimized move generation and evaluation (local bindings), and a golfed main-loop fallback. Local practice Elo mean 1,573 (trials 1,545 / 1,364 / 1,809) vs v3's 1,451 on the same level-9 kit; best single trial 1,809. Packed with LZMA from the readable engine.py source (main.py 4,027 bytes).

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:18081 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=1409h78a&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
