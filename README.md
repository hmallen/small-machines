# Small Machines

A static exhibit hall for the interactive single-file apps in this directory. Visitors open
[index.html](index.html), see all three machines running live, and press **OPERATE** to use one
full-screen. Deep links work (`#/crucible`, `#/primordium`, `#/pulsework`), Escape returns to
the hall, and the arrows in the top bar walk bay to bay.

## The machines

| Bay | Machine | File | What it is |
|----:|---------|------|------------|
| 01 | Crucible | `crucible.html` | Falling-sand elemental particle bench |
| 02 | Primordium | `primordium.html` | Evolution sandbox — petri dish of heritable creatures |
| 03 | Pulsework | `pulsework.html` | MK-I rhythm synthesizer — step sequencer + synth voices |

## Hosting

Everything is plain static files — no build step, no backend. Serve this directory with any
web server. The hall's live previews need HTTP (not `file://`) because they are same-origin
iframes.

Local:

```bash
python -m http.server 8907
```

Then open <http://localhost:8907/>. For real hosting, point nginx/Apache/Caddy at this
directory, or push it to any static host (GitHub Pages, Netlify, Cloudflare Pages). The only
external dependency is Google Fonts.

## Adding a machine

Drop a self-contained `whatever.html` next to `index.html` and add one entry to the
`MACHINES` array at the top of the script in `index.html` (slug, file, name, class line,
note, paint chip color). The hall builds the bay, the routing, and the viewer from that entry.

Notes for new entries:

- `attract: 'self'` — the app animates on its own (like Primordium).
- `attract: 'standby'` — leave the preview untouched (use this if the app persists state,
  like Pulsework's localStorage patterns).
- `attract: 'crucible'` is a bespoke driver for Crucible's public paint functions.
