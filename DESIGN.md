---
name: Small Machines
description: A soot-and-steel machine hall — three live exhibits mounted in bays off one gantry rail.
colors:
  soot: "#0b0c0d"
  steel: "#16181b"
  steel-2: "#1b1e22"
  plate: "#1a1d21"
  line: "#2b2f35"
  line-soft: "#22262b"
  bolt: "#3a3f46"
  chalk: "#e8e6df"
  ink-dim: "#9b9e98"
  ink-faint: "#8a8e85"
  hazard: "#ff5c1f"
  hazard-deep: "#b23c12"
  paint-crucible: "#c9a227"
  paint-primordium: "#4fd99b"
  paint-pulsework: "#ffb03a"
typography:
  display:
    fontFamily: "Big Shoulders Stencil, Arial Narrow, Franklin Gothic Medium, sans-serif"
    fontSize: "clamp(56px, 8.6vw, 118px)"
    fontWeight: 800
    lineHeight: 0.86
    letterSpacing: "0.015em"
  headline:
    fontFamily: "Big Shoulders Stencil, Arial Narrow, Franklin Gothic Medium, sans-serif"
    fontSize: "34px"
    fontWeight: 800
    lineHeight: 1
    letterSpacing: "0.03em"
  title:
    fontFamily: "Big Shoulders Stencil, Arial Narrow, Franklin Gothic Medium, sans-serif"
    fontSize: "17px"
    fontWeight: 700
    letterSpacing: "0.1em"
  body:
    fontFamily: "IBM Plex Mono, ui-monospace, Consolas, monospace"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: 1.55
  label:
    fontFamily: "IBM Plex Mono, ui-monospace, Consolas, monospace"
    fontSize: "11px"
    fontWeight: 600
    letterSpacing: "0.14em"
rounded:
  sm: "2px"
  md: "3px"
components:
  button-operate:
    backgroundColor: "{colors.hazard}"
    textColor: "{colors.soot}"
    rounded: "{rounded.sm}"
    padding: "9px 20px 10px"
  button-operate-hover:
    backgroundColor: "#ff6f38"
  button-bar:
    backgroundColor: "transparent"
    textColor: "{colors.ink-dim}"
    rounded: "{rounded.sm}"
    padding: "6px 12px"
  bay-frame:
    backgroundColor: "{colors.steel}"
    rounded: "{rounded.md}"
    padding: "10px"
  equipment-tag:
    backgroundColor: "{colors.plate}"
    rounded: "{rounded.md}"
    padding: "14px 16px 16px"
---

# Design System: Small Machines

## Overview

**Creative North Star: "The Plant Floor"**

The site shell is a machine hall — a turbine floor after dark, not a portfolio grid. Three
live machines hang in bays off one gantry rail; a hazard band crosses the top of the
building; equipment tags hang under each aperture with an address, a livery chip, a status
readout, and one OPERATE button. The world explicitly refuses the screenshot-card gallery:
nothing in the hall is a "card" — everything is plant equipment (a frame, a tag, a rail,
a stamp) that happens to carry information.

The hall itself is nearly achromatic: soot, steel, chalk, and one band of safety orange.
Every other color on the page is light escaping from the machines — the live feeds glowing
in their apertures and the tiny paint chips that carry each machine's livery. The three
exhibit apps (crucible.html, primordium.html, pulsework.html) each own their own committed
visual world; the shell's whole job is to frame them untouched. This document covers the
shell only.

**Key Characteristics:**
- Soot-and-steel achromatic ground; a fine concrete-grain noise overlay (5% opacity, screen blend) over the whole floor.
- Chalk stencil signage (Big Shoulders Stencil) against IBM Plex Mono plant-standard text; both faces uppercase almost everywhere.
- One safety-orange hazard color doing all interactive and status work.
- One governing gantry rail; bays hang from it by visible drop links.
- Live machines behind glass: real iframes, scaled down, inert, lamp-faded on.
- Industrial ephemera as ornament: screw heads, bolt lines, dotted leader rows, split-flap readouts, a rotated maker's stamp.

## Colors

An achromatic plant interior where the only chroma the hall owns is safety orange; all other color belongs to the machines.

### Primary
- **Hazard Orange** (#ff5c1f): the hall's single voice of chroma. Hazard strip, OPERATE button fill, focus rings, text selection, lit LEDs, link color in the noscript fallback, and the favicon plate. It always means "live / press here / caution".
- **Hazard Deep** (#b23c12): the darker rim of the same orange — the OPERATE button's border. Never used as a fill of its own.

### Tertiary
The machine liveries — foreign chroma the hall admits only as tiny paint chips on each equipment tag (9px squares that also glow with their own color). They belong to the machines, not the shell, and must never spread to shell surfaces.
- **Crucible Brass** (#c9a227): Crucible's livery chip.
- **Primordium Bloom** (#4fd99b): Primordium's livery chip.
- **Pulsework Amber** (#ffb03a): Pulsework's livery chip.

### Neutral
The dark neutrals form the project's own tonal scale, from floor to fitting:
- **Soot** (#0b0c0d): the deepest ground — page background (under a faint radial lift to #131417 at top center), scrollbar track, viewer background, and the text color on orange.
- **Steel** (#16181b) and **Steel 2** (#1b1e22): machined surfaces — bay frames and the hall bar are vertical gradients from steel-2 down to steel.
- **Plate** (#1a1d21): equipment-tag surface (gradient to #171a1e).
- **Line** (#2b2f35) and **Line Soft** (#22262b): borders and rules — frame borders, rail edges, tag borders, hairline dividers inside tags.
- **Bolt** (#3a3f46): the brightest fitting gray — screw heads, rail bolt heads, dotted leader lines, scrollbar thumb, the maker's-stamp border, hover border accents.
- **Chalk** (#e8e6df): primary text and stencil signage — a warm chalk white, never pure #fff.
- **Ink Dim** (#9b9e98) and **Ink Faint** (#8a8e85): secondary and tertiary text — plant-data rows, machine notes, statuses, labels, footer text.

### Named Rules
**The Machines Keep the Chroma Rule.** Shell surfaces are achromatic plus hazard orange, nothing else. All other chroma on the page must be machine light: the live feeds inside apertures and the per-machine paint chips. A new shell element never introduces a new hue.

**The Diegetic Glow Rule.** Glow is permitted only as lamp light from things that are lit: the LED's orange corona (0 0 8px 1px rgba(255,92,31,.55)), the paint chip's self-colored glow (0 0 6px 0 currentColor), and the OPERATE button's soft orange cast. Nothing glows for decoration.

## Typography

**Display Font:** Big Shoulders Stencil (with Arial Narrow, Franklin Gothic Medium fallback)
**Body Font:** IBM Plex Mono (with ui-monospace, Consolas fallback)

**Character:** Chalk-stenciled signage over plant-standard monospace. The stencil is loud, condensed, and always uppercase — it is paint on steel. The mono is the plant's paperwork: labels, registers, notes, statuses, with `font-variant-numeric: tabular-nums` set globally so every readout aligns.

### Hierarchy
- **Display** (stencil 800, clamp(56px, 8.6vw, 118px), line-height 0.86): the wordmark only. Its second line ("MACHINES") drops to weight 500, ink-dim, at roughly half size — one word painted bright, one word worn.
- **Headline** (stencil 800, 34px → 28px on mobile, line-height 1): machine names on equipment tags.
- **Title** (stencil 700, 17–19px, letter-spacing 0.08–0.1em): bay addresses ("BAY 01") and the viewer's title row. The OPERATE button (stencil 800, 18px) and maker's stamp (stencil 800, 15px) sit in this band.
- **Body** (mono 400, 14px base / 12.5px machine notes, line-height 1.55): descriptive text. Machine notes cap at 46ch.
- **Label** (mono 500–600, 10.5–12px, letter-spacing 0.1–0.18em, uppercase): equipment class lines, split-flap statuses (11px/600/0.14em), bar buttons, footer, plant-data register (12px).

### Named Rules
**The Stencil-Is-Signage Rule.** Big Shoulders Stencil appears only as signage: wordmark, machine names, bay addresses, OPERATE, the stamp, the viewer title. Everything that reads as data or prose is IBM Plex Mono. No third face, ever.

**The Plate Text Rule.** Small uppercase mono text is always functional plant data — an address, an equipment class, a status word, a register row. It never appears as a decorative kicker or eyebrow floating above a heading.

## Layout

The hall is one centered container (max-width 1320px, 28px side padding, 56px bottom) under a full-bleed 12px hazard strip. Vertical order is fixed: hazard strip → signboard header (wordmark left, dotted-leader plant-data register right, flex with baseline alignment) → the gantry rail → three bays → footer opened by the floor channel.

- **The rail** is a 10px steel extrusion (top border line #2b2f35, bottom line-soft, vertical gradient #1d2025 → #14161a) with bolt heads stamped every 72px via a repeating radial gradient.
- **Bays** are a 3-column grid, 30px gap, 34px below the rail; each bay hangs from a 2px drop link drawn from the rail to the frame (`.bay::before`).
- **The floor channel** (`.rail--channel`) is the rail's kin, not a second rail: 4px tall, no bolts, gradient reversed to read as a groove. It opens the footer.
- **Spacing rhythm** is bespoke, not tokenized: 10px frame padding, 12px frame-to-tag, 14–16px tag internals, 28–30px structural gaps, 44–56px section breathing. New shell work should stay in these bands rather than invent a scale.
- **Responsive:** below 1080px the bays stack single-column (max-width 640px, 44px gap) and drop links lengthen (30px first bay, 44px between stacked bays). Below 640px the hall tightens to 16px side padding, machine names drop to 28px, bar-button text hides leaving icon-only controls, and the footer row wraps.
- A fixed concrete-grain noise overlay (`body::after`, inline SVG fractal noise, opacity .05, mix-blend-mode screen) sits over everything at z-index 1; hall content lives above it at z-index 2.

### Named Rules
**The One Rail Rule.** Exactly one bolted gantry rail governs the page. Any further horizontal structure must be a channel — thinner, boltless, groove-shaded — never a second rail.

## Elevation & Depth

A hybrid: deep soft black drop shadows push machined plates off the soot floor, while 1px inset white highlights (`inset 0 1px 0 rgba(255,255,255,.04–.28)`) catch light on each plate's top edge so surfaces read as milled steel. Apertures go the other way — inset vignettes pull them into the wall. The only luminous shadows are the diegetic glows (see Colors).

### Shadow Vocabulary
- **Frame lift** (`box-shadow: 0 18px 40px rgba(0,0,0,.5), inset 0 1px 0 rgba(255,255,255,.05)`): bay frames — the heaviest lift in the hall.
- **Tag lift** (`box-shadow: 0 10px 24px rgba(0,0,0,.35)`): equipment tags — half the frame's weight.
- **Aperture well** (`box-shadow: inset 0 0 0 1px rgba(255,255,255,.04), inset 0 0 34px rgba(0,0,0,.7)`): the window into the machine, plus a diagonal glass glare overlay (`linear-gradient(165deg, rgba(255,255,255,.05), transparent 22%)`).
- **Operate cast** (`box-shadow: 0 4px 14px rgba(255,92,31,.22), inset 0 1px 0 rgba(255,255,255,.28)`): orange lamp cast under the button; deepens to `0 7px 18px rgba(255,92,31,.3)` on hover.
- **LED corona** (`box-shadow: 0 0 8px 1px rgba(255,92,31,.55)`): lit LEDs only; unlit LEDs carry an inset socket shadow (`inset 0 1px 1px rgba(0,0,0,.6)`).
- **Chalk drop** (`text-shadow: 0 2px 0 rgba(0,0,0,.6)`): the wordmark's hard paint shadow — the one hard-edged shadow in the system, reserved for the wordmark.

### Named Rules
**The Milled Edge Rule.** Every raised plate pairs its drop shadow with a faint 1px inset top highlight. A shadow without its edge highlight reads as paper, not steel.

## Shapes

Machined, near-square geometry. Radii are 2px (apertures, buttons, stamps, paint chips) and 3px (frames, tags) — just enough to read as deburred metal, never rounded-card softness. The only circles are functional hardware: screw heads (10px stroked SVG circles in each frame corner), rail bolt heads, and the 7px LED dot. Recurring silhouettes: 135° hazard striping (16px orange / 16px near-black repeat), dotted leader lines connecting register labels to values, 2px drop links, and the maker's stamp rotated -2°. Icons are small inline stroked SVGs (arrows, external-link, chevrons) at 1.2–1.6px stroke — no icon fonts, no glyph characters.

## Components

### Hazard Strip
The building's safety band: a full-bleed 12px strip of 135° repeating stripes, `#ff5c1f` on `#141518` (16px each), with a 1px black bottom border and a faint white top-light. Appears once, at the very top. It is architecture, not a divider — never reuse it mid-page.

### Gantry Rail
- **Rail** (10px): bolted steel extrusion; see Layout for construction. Sits between header and bays.
- **Channel variant** (`.rail--channel`, 4px): boltless floor groove opening the footer.

### Bay (frame + aperture + lamp)
- **Frame:** steel gradient plate, 1px line border, 3px radius, 10px padding, frame-lift shadow, four corner screws. Border lightens to #3d434b on hover/focus-within (0.18s).
- **Aperture:** black window (2px radius, overflow hidden) holding a live iframe feed scaled from a 1220×860 design size by `transform: scale()`; aperture height is computed to keep that aspect. Feeds are decorative and fully inert: `pointer-events: none`, `aria-hidden`, `tabindex="-1"`, lazy-loaded, scrollbars suppressed by injected style. Feed brightens 8% on bay hover.
- **Lamp:** a black cover over the feed that fades out over 1.1s (cubic-bezier(.16,1,.3,1)) when the feed loads — machines come on with the lamps.
- **Hit plate:** an invisible full-aperture button (aria-hidden, tabindex -1; the OPERATE button is the accessible path) that opens the machine; orange inset focus ring.

### Equipment Tag
The information plate under each aperture: plate-gradient surface, line-soft border, 3px radius, 14/16px padding, tag-lift shadow. Fixed anatomy top to bottom: address row (stencil "BAY NN" + paint chip + right-aligned LED and split-flap status, closed by a hairline rule), machine name (headline stencil), equipment class (label mono), note (12.5px mono, ≤46ch), then the ops row pinned to the bottom (OPERATE left, standalone link right).

### Paint Chip
9px square, 2px radius, filled and glowing with its machine's livery color, dark 1px rim. The only place foreign chroma touches shell chrome.

### LED + Split-Flap Status
- **LED:** 7px circle; unlit = #2c2f34 with socket inset; lit = hazard orange with corona.
- **Split-flap** (`.flap`): uppercase mono status word (11px/600/.14em) whose letters tick in like a departure board — each cell flips (0.34s, steps(2)) through 2–4 random glyphs from `ABCDEFGHIJKLMNOPQRSTUVWXYZ/#` before landing, staggered 12ms per letter over a 70ms base tick. Vocabulary observed: POWERING → RUNNING / STANDBY (bays), OPERATING (viewer).

### Operate Button
The one loud control: stencil 800 uppercase, hazard fill on soot text, hazard-deep border, 2px radius, arrow SVG. Hover: lifts 1px, fill warms to #ff6f38, cast deepens; active returns to rest. Each tag also carries a quiet counterpart — the **standalone link** (10.5px mono uppercase, ink-faint, external-link SVG, dotted bolt underline on hover) linking to the machine's own file.

### Hall Bar (viewer chrome)
46px steel bar over the live machine: back button, stencil title ("BAY NN" in ink-faint + machine name), prev/next chevron switch, lit LED, and an OPERATING split-flap. **Bar buttons:** transparent, 1px line border, 2px radius, mono 11px/600 uppercase, ink-dim; hover brightens text to chalk and border to bolt. On mobile, button labels hide to icons.

### Viewer Overlay
Full-viewport fixed dialog (`role="dialog" aria-modal="true"`, soot background): hall bar on top, the machine's iframe filling the rest at full interactivity (unlike bay feeds). Routing and containment conventions:
- **Hash routes:** `#/{slug}` opens a machine; empty hash is the hall. `applyHash` runs on load and on `hashchange`, so deep links and back/forward work.
- **Containment:** while open, the hall gets `inert`, body scroll locks, focus moves to the back button; on close the iframe unloads to `about:blank`, inert and scroll release, and focus returns to where it was.
- **Escape** closes; prev/next cycle through the register; `document.title` becomes "{Machine} — Small Machines".

### Maker's Stamp
Corner-locked provenance in the footer: "SM/26" in stencil 800/15px, 1.5px bolt border, 2px radius, rotated -2° — an inspection stamp, not a logo. Lives at the end of the footer row.

### Plant-Data Register
The header's right-hand log: 12px mono rows, each a label and bold chalk value joined by a dotted bolt leader line. Also the pattern for any future tabular shell data.

### The Register (adding machines)
The hall is data-driven from the `MACHINES` array in index.html: slug, file, name, klass, note, paint, attract. **Adding a machine is one entry there** (plus its self-contained .html beside index.html and, if it gets a livery, one `--paint-*` custom property). Bay addresses, tags, feeds, routing, and viewer switching all derive from it. An **attract drive** may operate an idle machine through its own public controls (Crucible gets painted strokes); it must be defensive — wrapped in try/catch, paused when hidden or off-screen, and silently absent if the machine's internals change.

### Motion Grammar
- **Easing:** `cubic-bezier(.16, 1, .3, 1)` — a fast-out settle — for all entrance motion; plain 0.12–0.2s transitions for micro-state (buttons, borders, LEDs).
- **Power-up:** on load the bays rise 14px and fade in over 0.7s, staggered 0.12s left to right — the hall coming online, once, on entry only.
- **Lamp fade:** 1.1s opacity fade revealing each feed on load.
- **Split-flap ticks:** as specified above; letters, never fades.
- **Micro-motion:** OPERATE lifts 1px on hover; feeds brighten on bay hover; nothing else moves.
- **Reduced motion:** with `prefers-reduced-motion: reduce`, everything resolves instantly — bays appear in place, lamps cut straight to the feed, flap letters set without ticking, OPERATE stops translating, and the attract drive never starts. No slowed-down versions; motion is simply absent.

## Do's and Don'ts

### Do:
- **Do** keep every shell surface inside the soot–steel–chalk neutrals plus hazard orange; new chroma may only arrive as a machine's own light or livery chip.
- **Do** pair every raised plate with both its soft black drop shadow and its 1px inset top highlight (The Milled Edge Rule).
- **Do** add machines by appending one `MACHINES` entry (plus the machine's own file and `--paint-*` chip color); never hand-build a bay.
- **Do** keep bay preview iframes inert: `pointer-events: none`, aria-hidden, tabindex -1, lazy, scrollbars suppressed. Scrollbar suppression is the only styling the shell may inject into a machine.
- **Do** treat bay numbers as functional addresses ("BAY 01", zero-padded) that carry through tag, viewer title, and hash-driven state.
- **Do** honor reduced motion by removing motion entirely, including the attract drive.
- **Do** keep stencil for signage and mono for data, both almost always uppercase, with tabular numerals.

### Don't:
- **Don't** restyle, patch, or theme the three machines — their files are finished artifacts and each owns its full viewport inside frame and viewer.
- **Don't** add a second rail; further horizontal structure is a boltless channel (The One Rail Rule).
- **Don't** introduce decorative kickers or eyebrows; small uppercase text exists only as plant data (The Plate Text Rule).
- **Don't** use glow, outer color casts, or luminous borders on anything that isn't diegetically lit (LED, paint chip, OPERATE).
- **Don't** exceed 3px radii or introduce pills, circles-as-decoration, or card-like softness; circles are hardware only.
- **Don't** use icon fonts, emoji, or glyph characters as icons; icons are small inline stroked SVGs.
- **Don't** rebuild the hall as a screenshot-card gallery; previews are live machines behind glass or they are not previews.
