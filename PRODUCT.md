# PRODUCT

## What this is
A personal collection of small interactive machines — self-contained single-file HTML apps —
served as a static site. The showcase (index.html) is an exhibit hall: visitors pick a machine
and play it in place.

## The machines (exhibits)
- **Crucible** (`crucible.html`) — falling-sand elemental particle bench. Paint elements, watch
  them react. Identity: dark alchemical workshop, brass on soot, Cinzel + IBM Plex Mono.
- **Primordium** (`primordium.html`) — evolution sandbox in a petri dish; creatures with heritable
  traits (speed, size, sense) live, eat, breed, die out. Identity: bioluminescent darkfield lab,
  green-on-near-black, Bricolage Grotesque + IBM Plex Mono.
- **Pulsework** (`pulsework.html`) — MK-I rhythm synthesizer; step sequencer with synthesized
  drum voices. Identity: amber hardware faceplate, Chakra Petch + IBM Plex Mono.

Common thread: each is a simulation of emergent behavior you poke with your hands. Each app owns
its full viewport and its own committed visual world; the shell must frame them, never restyle them.

## Audience & tone
Friends and curious visitors who receive the link. Tone: playful exhibit hall — atmospheric,
fun, a dark gallery of live machines. Not portfolio-formal.

## Platform & constraints
- Pure static hosting: any web server (nginx, GitHub Pages, `python -m http.server`). No build
  step, no backend, no bundler.
- The three project files are finished artifacts and must not be modified.
- Apps embed via iframe (they are self-contained; only external dependency is Google Fonts).
- Adding a future machine should be a one-entry edit in index.html.

## Brand commitments
- Collection name: **Small Machines** (chosen for the site wordmark; exhibit-hall flavored).
- No other pinned brand assets. The shell's visual world is free, provided each machine's own
  identity stays untouched inside its frame.
