# tiny-chess-01 — a chess engine in 4,082 bytes of Python

An original compact chess engine for make.fun's tiny-chess-01 bounty.
`main.py` is the whole engine: an LZMA-packed build (made with the kit's
`makefun compress`) of the readable source kept beside it during the
build. It plays the house gauntlet through the env at MAKEFUN_ENV_URL
(POST /game, POST /move), searching to a fixed budget of 65,000 nodes a
move — no clock is ever read, so every trial replays move for move.

Inside: 0x88 board, negamax alpha-beta with PVS, a transposition table
kept across moves, quiescence over captures, promotions and check
evasions, check extensions, LMR, killer moves, and a tapered
material + piece-square evaluation with passed-pawn terms.

Python 3.13, standard library only. MIT licensed.
