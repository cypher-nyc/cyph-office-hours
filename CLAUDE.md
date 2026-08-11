# CYPH — Office Hours Deck

## What this is

The office-hours recruiting deck for Cyph (cypher.nyc). A sibling to `cyph-deck` (investor pitch) and `cyph-venue-partnerships` (venue deck), built from the same HTML/CSS/JS shell but rewritten to recruit experts — academics, writers, practitioners, street-legends with earned knowledge — into hosting office hours on the platform.

No typology of "who we want" (experts can be anyone). The pitch is rooted in the underground: "here are the thinkers already on this map; we'd love to add you." Brevity matches the venue deck — 7 slides, no financials. The close ask is "become an office hours host; scheduling, rates, logistics later."

## Slide map (5 slides, s0–s4)

Trimmed from the venue-partnerships scaffold — the "why we want you on cyph." and "the underground." slides were intentionally removed, "what we hand you" lost its standalone slide and was merged into the close, and the isometric "what we are building." slide was added (ported from `cyph-deck`'s how-it-works slide).

- `s0` title — "cyph." / "the new underground for ideas."
- `s1` founders — Jalen + Bryan badges (unchanged).
- `s2` **what we are building.** — Stacked isometric layer stack copied from `cyph-deck` s5 ("how it works"). Same three layer images (l1/l2/l3 color+bw) and same 4-step layer annotation panel (underground → cyph → irl → ∞). Header reads "what we are building" instead of "how it works". The original `cyph-deck` layer copy is kept verbatim (including `irl`: "touch grass." and the ∞ panel). Sub-step navigation (1–4) cycles through the layer stack on this slide. This is the slide the `host` nav button targets.
- `s3` **we're venture backed.** — SVG trajectory chart: 1K (today) → 10K → 100K → 1M → 3M. Subheadline "we'd love to work with you now — and when we blow up."
- `s4` **close (what we hand you + become an office hours host).** — The 4-card grid that used to be its own slide ((01) a matched audience, (02) context, prepped, (03) your archive, resurfaced, (04) paid + amplified) is now the top of the close slide, followed by the CTA headline "become an office hours host." and contact emails + rebrand disclaimer.

## What to keep in sync

Anything shared with `cyph-deck` and `cyph-venue-partnerships` should stay visually consistent — founders cards, trajectory chart SVG, background layers, fit-to-viewport scaling, auth gate. Assets live at the same paths; all three decks currently share the same `assets/` tree (copied at scaffold time).

## Nav

Four buttons: `cyph` / `founders` / `host` / `close`. The `host` button targets the isometric `s2` "what we are building." slide. `close` targets `s4`.

## Layer-stack copy (deck.js)

`layerInfo` in `deck.js` uses the original `cyph-deck` layer copy verbatim for all four layers (underground, cyph, irl, ∞). No office-hours-specific rewrites.

## Color scheme

Unchanged from cyph-deck — Cornflower `#608FE6`, Paprika `#EC4E20`, Deep Space `#13293D`, Amaranth `#6D1A36`, Amber `#FBAF00`. Cream `#ede8de` backgrounds.

## Slide structure

5 slides, IDs `s0`–`s4`. `T = 5` in `deck.js`. Counter reads `XX/05`.

## Key files

- `index.html` — all slide content
- `styles.css` — all styles (shared, unchanged)
- `deck.js` — navigation, animations, chapter mapping, layer-stack descriptions
- `assets/` — shared tree copied from cyph-venue-partnerships at scaffold time
