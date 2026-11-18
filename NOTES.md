# Build and testing notes

`engine_m.py` (readable source, 11,017 bytes) is packed into `main.py`
with the kit's `makefun compress`, run as its own command after the
final source edit. It is deliberately NOT committed — it would break
the per-file cap; the bundle uploads it beside the sessions. Snapshot:
main.py 4,082 (cap 4,096) + LICENSE + README.md + this file = 7,418
bytes, under the 8,192 cap, with room for the claim file.

Correctness: perft matches the known counts exactly on the six standard
positions — startpos 20/400/8902/197281, Kiwipete 48/2039/97862,
talkchess positions 3–6 (43238, 9467, 62379, 89890 at tested depths) —
covering castling, en passant pins, and promotions.

Local gauntlet (kit env, practice trial-0, 6 games), final packed
main.py run as `python3 -P -s main.py`, 65,000 nodes/move: W4 D0 L2
(wins vs depth-2, depth-3, nodes-100k, nodes-250k; losses vs depth-4,
nodes-500k; all by checkmate, no time losses; 550 s of 1,800 s).
4.0/6 rates ≈ Elo 1,455 on the published anchors; the house baseline
(sunfish-4k) rates 1,364 on this instance. A fuller-featured source
build scored 5/6 but packed to 6,502 bytes — the byte cap, not the
search design, is the binding constraint.

Weaknesses: no null-move/futility/delta pruning, no history heuristic,
no game-history repetition scoring (in-search path repetition scores
0), endgame king on the middlegame table, MVV-LVA ordering without SEE.
One instance carries ±~100 Elo of noise.
