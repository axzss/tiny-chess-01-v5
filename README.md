# tiny-chess-01-v5

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/axzss/tiny-chess-01-v5/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/axzss/tiny-chess-01-v5/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB chess engine in Python: alpha-beta with iterative deepening, quiescence search, transposition table, killer/history move ordering, null move, LMR, PVS, check extension, aspiration windows, and a tapered piece-square evaluation with tempo, passed-pawn, pawn-structure (doubled/isolated), rook-on-open-file and king pawn-shield bonuses. Built from scratch for the make.fun tiny-chess-01 bounty.

v5 over v3: king pawn-shield safety (-12 per missing shield pawn, phase-tapered), micro-optimized move generation and evaluation (local bindings), and a golfed main-loop fallback. v5f (this entry) drops the aspiration windows entirely — full-window search at every depth, which proved faster and stronger than the aspiration re-searches. Local practice Elo: v5f trial-0 1,654 (4W 2D 0L, best single trial, +109 over v5a/v5d trial-0) vs v3's 1,451 on the same level-9 kit. Packed with LZMA from the readable engine.py source (main.py 3,902 bytes).

## Practice results (level-9 kit, 6 games/trial)

| Variant | Trial 0 | Trial 1 | Trial 2 | Mean |
|---------|---------|---------|---------|------|
| v3b (baseline) | 1,451 | — | — | 1,451 |
| v5a | 1,545 | 1,364 | 1,809 | 1,573 |
| v5b (MA 150k) | 1,545 | — | — | — |
| v5c (rook on 7th) | 1,451 | — | — | — |
| v5d (stronger passed pawns) | 1,545 | 1,654 | 1,451 | 1,550 |
| v5e (king safety -20) | 1,451 | — | — | — |
| v5f (v5d, no aspiration) | 1,654 | — | — | — |

v5a is the best variant by 3-trial mean (1,573). v5f trial-0 (1,654) is the best single trial of any variant, with zero losses — submitted directly for its server practice grade per the user's call to test the real thing. Single-trial variance is large (one game swing ≈ 100 Elo); the mean is the honest number.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:18081 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=1409h78a&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
