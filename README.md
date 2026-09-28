# Wild Gambit

Chess where every turn starts with a card draw. Built for the iPhone browser; one self-contained `index.html`, no build step.

Open `index.html` in Safari (or host it anywhere, e.g. GitHub Pages) and use Share → Add to Home Screen for a full-screen app.

## How a turn works

You hold a hand of 3 cards. Each turn you refill to 3, then play one.

| Card | Effect |
| --- | --- |
| Number 1–4 | Move that many different pieces, one move each (weighted to 1s and 2s) |
| +2 / +3 / Wild +4 | Bring back up to that many of your captured pieces to their starting squares (queen counts 2; promoted pawns return as pawns). Reviving is the whole turn |
| Reverse | The board spins and you go again: refill and play another card |
| Wild | Turn over two cards and keep one |
| Skip | Never enters your hand: drawing one costs you that turn (redrawn if you're in check) |

Chess rules are standard. Each piece moves at most once per turn, giving check ends the turn, and your king only has to be safe when your turn ends. Checkmate is judged against your hand: you lose only if no card you hold can save the king.

## Packs, tricks and enhancements

The Back Room offers two booster packs per visit:
- **Trick Pack** ($4): pick 1 of 3 tricks. You can carry 2. Match tricks are used on your turn before you play a card: Fresh Hand, Scry, Hourglass (+2 turns), Switcheroo (swap two pieces), Raise Dead, Bounty Board (double score this turn), Cold Feet (opponent draws a Skip) and Sharpen. Deck tricks are used in the shop: Gild, Glaze, Temper, Clover, Promote and Ember.
- **Card Pack** ($4): pick 1 of 3 cards for your deck, often enhanced.
- **Joker Pack** ($6): pick 1 of 2 jokers.

Enhancements stay on a card for the whole run: **Gold** (+$2 when played), **Glass** (+1 move or revive, 1 in 4 chance to shatter), **Steel** (+2 mult on captures that turn), **Lucky** (1 in 3 chance of +$3).

## Modes

- **Run**: 8 AI opponents. Each level gives you 12 turns to reach a score; captures score chips × mult (pawn 1, knight/bishop 3, rook 5, queen 9, × a multiplier jokers raise). Checkmate wins outright. Wins pay cash, $1 per unused turn (max $5) and interest. Spend it on jokers (30 kinds, 5 slots) and deck edits in the Back Room. Missing a target or getting mated ends the run.
- **Pass & play**: two people on one phone, checkmate only; the top rail is rotated for the player across the table.

Progress is saved in `localStorage`. The AI runs in a Web Worker; the swirling background is a small WebGL shader.

## Testing tools

- **Deck viewer**: the deck button in the top bar shows what's left in your draw pile, the odds of each card, and your average draw.
- **Debug mode**: tap the Wild Gambit logo 5 times (or open the page with `#debug`). A green DBG button appears in matches with fast animations, instant AI, auto-play for your side, card stacking for either player, win/lose buttons, quick endgame and in-check setups, +$25, level jumping and a joker toggle list.
