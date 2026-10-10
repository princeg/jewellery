# Mermaid's Jewel Box

A shiny underwater dress-up game. Pick jewellery from the treasure tray and
put it on a mermaid — or on any of her five friends.

![single file](https://img.shields.io/badge/build-none%20required-F6C450) ![vanilla](https://img.shields.io/badge/stack-HTML%20%2B%20SVG%20%2B%20canvas-7FEFE2)

## Play

Open `index.html` in any browser. There is no build step and no dependencies —
the whole game is one file.

## How it works

- **Tap a jewel to put it on, tap it again to take it off.** Every piece knows
  where it belongs, so earrings always land on ears and bands always land on
  the tail or ankles.
- **28 pieces** across six shelves: crowns & tiaras, earrings, necklaces,
  bracelets, brooches, and anklets & tail bands.
- **Six characters**, each remembering their own outfit — switch with the gold
  arrows or the left/right arrow keys:
  Marina the Mermaid, Bluey the Pup, Luna the Unicorn, Mochi the Kitty,
  Ember the Dragon, and Pip the Bunny.
- **Shine meter** fills as more jewellery goes on. Six out of six earns a
  sparkle shower.
- **Surprise me!** rolls a random full outfit; **Take it all off** clears it.

## Adding to the game

Everything lives in the `<script>` block at the bottom of `index.html`.

- **A new jewel**: add an entry to `ITEMS` with a `slot`
  (`crown`, `ears`, `neck`, `wrist`, `brooch`, `low`) and an SVG string drawn
  around `(0,0)` — crowns sit above the anchor, earrings and necklaces hang
  below it, everything else is centred on it.
- **A new character**: add an entry to `CHARACTERS`. Most friends reuse the
  shared `critter()` body and `SLOTS_CRITTER` anchor points, so a new one is
  usually just fur colours plus ears, a tail and any horns.

## Accessibility

Keyboard-operable, visible focus rings, and all animation (shimmer, bubbles,
sparkles) switches off under `prefers-reduced-motion`.
