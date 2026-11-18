# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/cubinmark/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/cubinmark/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

The entry for make.fun's tiny-chess-01 bounty: a complete chess engine in a 4,082-byte `main.py` (cap 4,096), an LZMA-packed build (made with the kit's `makefun compress`) of the readable source kept beside it during the build. 0x88 board, negamax alpha-beta with PVS, transposition table, quiescence, check extensions, LMR, killer moves and tapered piece-square evaluation, on a fixed 65,000-node budget per move so play is fully deterministic. Perft-exact on the standard suite; scored 4/6 against the house gauntlet in local trials, above the house baseline. See NOTES.md for the testing record.

## Run it

```sh
MAKEFUN_ENV_URL=<suite base URL> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=dnrr099a&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
