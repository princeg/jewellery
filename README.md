# Mermaid's Jewel Box

A shiny underwater dress-up game. Pick dresses, shoes, makeup and jewellery
from the treasure tray and put them on a mermaid — or on any of her
forty-nine friends.

![single file](https://img.shields.io/badge/build-none%20required-F6C450) ![vanilla](https://img.shields.io/badge/stack-HTML%20%2B%20SVG%20%2B%20canvas-7FEFE2)

## Play

Open `index.html` in any browser. There is no build step and no dependencies —
the whole game is one file.

## How it works

- **Tap a jewel to put it on, tap it again to take it off.** Every piece knows
  where it belongs, so earrings always land on ears and bands always land on
  the tail or ankles.
- **62 pieces** across ten shelves: dresses & gowns, eye makeup, lips & blush,
  crowns & tiaras,
  earrings, necklaces, bracelets, brooches, anklets & tail bands, and shoes &
  slippers. Dresses go on first, so the jewellery always sits on top of them.
  Shoes know where each friend's feet are — paws, flippers, stumpy bird legs,
  octopus tentacles, or a mermaid's fluke. Makeup works the same way: eight eye
  looks and eight lip colours anchor to each friend's own face, so they land
  right on a frog's bulging eyes, a goggle-wearing buddy, or an alligator's
  snout.
- **50 characters**, each remembering their own outfit — switch with the gold
  arrows or the left/right arrow keys, or tap **All 50 friends** for the whole
  list. Mermaids, princesses and a fairy; dogs, cats, bunnies and farm animals;
  lions, tigers, elephants and giraffes; an alligator, three dinosaurs and a
  dragon; owls, flamingos, bees and butterflies; an octopus, a robot, an alien
  and a goggle-wearing yellow buddy.
- **Shine meter** fills as more goes on. Ten out of ten earns a sparkle
  shower, and every one of the fifty can reach it.
- **Surprise me!** rolls a random full outfit; **Take it all off** clears it.
- **Music and sounds.** A slow underwater melody plus a chime for every piece
  you put on. The speaker button on the stage mutes it, and the choice is
  remembered. All of it is generated with the Web Audio API, so there are no
  audio files to download.

## On an iPad

The whole game fits on one screen from 760px wide up, in either orientation --
the mermaid scales to the height available and the jewellery tray scrolls on
its own, so nothing important slides off the bottom. Browsers only allow sound
after a tap, so the music starts on your first touch. If the iPad is on silent,
Web Audio stays muted too.

## Adding to the game

Everything lives in the `<script>` block at the bottom of `index.html`.

- **A new jewel or dress**: add an entry to `ITEMS` with a `slot`
  (`dress`, `eyes`, `lips`, `crown`, `ears`, `neck`, `wrist`, `brooch`, `low`,
  `shoes`) and an SVG string drawn
  around `(0,0)` — crowns sit above the anchor, earrings and necklaces hang
  below it, everything else is centred on it.
- **A new character**: add an `R_(...)` entry to `ROSTER`. Nearly every friend
  is the shared `critter()` body with different colours and a choice of ears
  (`round`, `pointy`, `floppy`, `hang`, `long`, `tiny`, `big`, `tuft`, `tufts`,
  `horns`), tail (`thin`, `bushy`, `puff`, `curl`, `long`, `tufted`, `fish`)
  and legs (`stand`, `fins`, `tentacles`, `stump`, `none`), plus optional
  markings from `MARK` — spots, stripes, wool, wings, a shell, a snout,
  goggles. That shared body is what lets one necklace fit a bunny, a
  triceratops and a robot. Mermaids (`m`) and princesses (`p`) have their own
  shapes.

## Accessibility

Keyboard-operable, visible focus rings, and all animation (shimmer, bubbles,
sparkles) switches off under `prefers-reduced-motion`.
