# BATTY

A block breaker in the browser, a tribute to **Batty** (Elite, ZX Spectrum,
1987). Everything is in a single `index.html` — no libraries, no build step.

**[▶ Play it here](https://ulebule.github.io/batty/)**

## Controls

| Key | Action |
|---|---|
| `◀` `▶` | move the bat |
| `Space` / `▲` | launch the ball, fire the laser |
| `Enter` | start / new game |
| `P` | pause |
| `M` | sound on / off |
| `L` | language |

On a touch screen you slide a finger to move the bat and tap to launch or
fire. On the title screen, tapping the row of language codes along the bottom
cycles the language — the `L` key does the same, and the choice is remembered.

## The game

Clear every brick to move on. Silver bricks take several hits and gold ones
cannot be broken at all, so some walls have to be worked around. Falling
capsules change the run: a longer bat, a slower ball, lasers, extra balls, an
extra life, or a warp straight to the next level. Aliens drift in and drop
bombs; shoot them for points.

The hi-score table is shared online — scores are stored in Firebase and the
board shows everyone's runs. With no connection the game keeps working and
falls back to scores stored in the browser.

## Languages

English, Slovenian, German, Italian and French, detected from the device and
switchable with `L`.

## Install it

The game is a PWA: a browser will offer to add it to the home screen (on iOS,
Share → *Add to Home Screen*), and it then opens standalone, without browser
chrome. A service worker caches `index.html`, the manifest and the icons, so
after the first visit the game runs with no connection at all. The online score
board naturally needs the network; offline it falls back to local scores.

The worker only touches same-origin requests, and the cache key is prefixed
with the repo name — the other games published under `ulebule.github.io` keep
their own caches instead of evicting each other.

## Licence

MIT
