# cyph-office-hours

The office-hours host recruiting deck for Cyph: a six-slide single-page HTML/CSS/JS presentation built from the same shell as `cyph-deck` and `cyph-venue-partnerships`. Layer: Subsidiary/site.

## Talks to

Standalone: yes. No platform service is called. The shared things are a local copy of the `auth.js` email gate (same Google Apps Script logger as cyph-deck, older script-tag contract without `data-mode`) and the `assets/` tree copied from `cyph-venue-partnerships`.

| Service | Direction | Protocol | For what |
|---|---|---|---|
| Google Apps Script web app (`LOG_URL` in `auth.js`) | out | HTTPS POST (`fetch` / `sendBeacon`) | email gate + access log; silent no-op if `LOG_URL` is empty |
| cdnjs (anime.js 3.2.2) | out | script tag | slide animations |

Events published/subscribed: none.

## Stack

- Static HTML, CSS, vanilla JS; no package.json, no build.
- No port, no database, no store. `auth.js` bypasses the gate on `localhost`, `127.0.0.1` and file://.
- Deploy target: none in this repo (no workflow, no bucket config).

## Layout

```
index.html    all slide content: s0 title, s1 founders, s2 what we are building (isometric layer stack),
              s3 what we hand you, s4 we're venture backed (SVG trajectory), s5 close; HUD nav cyph/founders/building/host/close
styles.css    all styles (shared shell)
deck.js       navigation, chapter map, per-slide animations, layerInfo copy for the layer stack (T = 6)
auth.js       email gate + access logging
assets/       shared image tree (layers, people, brands, backgrounds, moments, cards, icons, reference)
favicon.png
```

## Run / test / lint

```
open /Users/cash/Documents/github/cyph/cyph-office-hours/index.html    # or any static file server on localhost
```

No tests, no lint, no build.

## Rules for changing this repo

- Slide IDs `s0..s5` must stay contiguous; `deck.js` indexes `getElementById("s" + i)`. Adding or removing a slide is a lockstep edit of `index.html`, both HUD counters (`#hudCtr`, `#bhudCtr`, `XX/06`), and `deck.js` (`T`, the `ch` chapter map, the counter strings, the per-slide animation cases).
- Founders cards, trajectory chart SVG, background layers, fit-to-viewport scaling and the auth gate must stay visually consistent with `cyph-deck` and `cyph-venue-partnerships`.
- `layerInfo` in `deck.js` keeps the original `cyph-deck` layer copy verbatim (underground, cyph, irl, infinity); no office-hours-specific rewrites.
- Copy is Cash-authored; only make dictated wording changes. No typology of "who we want"; the close ask is "become an office hours host; scheduling, rates, logistics later."
- Colors: Cornflower `#608FE6`, Paprika `#EC4E20`, Deep Space `#13293D`, Amaranth `#6D1A36`, Amber `#FBAF00`; cream `#ede8de` backgrounds. Do not introduce others.

## Deploy

Not wired. The repo holds no workflow and no hosting config; hosting follows the `cyph-deck` pattern (S3 + CloudFront or GitHub Pages) when it ships.
