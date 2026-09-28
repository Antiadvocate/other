# Wild Gambit

Chess where every turn starts with a card draw. Built for the iPhone browser; one self-contained `index.html`, no build step.

Open `index.html` in Safari (or host it anywhere, e.g. GitHub Pages) and use Share → Add to Home Screen for a full-screen app.

## Cards

| Card | Effect |
| --- | --- |
| Number 1–4 | Move that many different pieces, one move each. The deck is weighted low (three 1s, two 2s, one 3, one 4 per color), so a turn averages 2 moves |
| +2 / +3 / Wild +4 | Bring back up to that many of your captured pieces, to their starting squares (nearest free back-rank square if taken). A queen counts as 2; a promoted pawn returns as a pawn. Reviving is the whole turn. With nothing to revive, or while in check, it plays as a 1 |
| Skip | Lose your turn (one move instead if you're in check) |
| Reverse | The board flips: players swap armies, and the opponent moves next with the side that was to move |
| Wild | Turn over two cards and keep one |

Chess rules are standard (castling, en passant, promotion, checkmate, stalemate). Each piece moves at most once per turn, and giving check ends the turn. Your king only has to be safe when your turn ends, so checkmate is decided after the draw: you lose only if the card you drew can't get your king out of check.

## Modes

- **Run**: 8 AI opponents with rising search depth and rule twists. Wins pay cash plus interest. Spend it on jokers (25 kinds, 5 slots) and deck edits in the Back Room. One loss ends the run.
- **Pass & play**: two people on one phone; the top rail is rotated for the player across the table.

Progress is saved in `localStorage`. The AI runs in a Web Worker so animations stay smooth while it thinks.

## Testing tools

- **Deck viewer**: the deck button in the top bar shows what's left in your draw pile, the odds of each card, and your average draw.
- **Debug mode**: tap the Wild Gambit logo 5 times (or open the page with `#debug`). A green DBG button appears in matches with fast animations, instant AI, auto-play for your side, card stacking for either player, win/lose buttons, quick endgame and in-check setups, +$25, level jumping and a joker toggle list.
