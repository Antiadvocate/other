# Wild Gambit

Chess where every turn starts with a card draw. Built for the iPhone browser; one self-contained `index.html`, no build step.

Open `index.html` in Safari (or host it anywhere, e.g. GitHub Pages) and use Share → Add to Home Screen for a full-screen app.

## Cards

| Card | Effect |
| --- | --- |
| Number 1–4 | Move that many different pieces, one move each. The deck is weighted low (three 1s, two 2s, one 3, one 4 per color), so a turn averages 2 moves |
| +2 / +3 | Move one piece that many times in a row. A capture ends the run |
| Wild +4 | One piece, four moves |
| Skip | Lose your turn (one move instead if you're in check) |
| Reverse | The board flips: players swap armies, and the opponent moves next with the side that was to move |
| Wild | Turn over two cards and keep one |

Chess rules are standard (castling, en passant, promotion, checkmate, stalemate). Giving check ends your turn, and a + card run stops at a capture, so a capturing piece can always be answered.

## Modes

- **Run**: 8 AI opponents with rising search depth and rule twists. Wins pay cash plus interest. Spend it on jokers (25 kinds, 5 slots) and deck edits in the Back Room. One loss ends the run.
- **Pass & play**: two people on one phone; the top rail is rotated for the player across the table.

Progress is saved in `localStorage`. The AI runs in a Web Worker so animations stay smooth while it thinks.
