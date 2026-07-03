# ONYX SUPPLY — Midnight Drop

Cinematic e-commerce concept site for a fictional premium streetwear label. One
self-contained HTML file plus AI-generated footage (Seedance 2.0 via Higgsfield,
std mode, 1080p, silent), all anchored to a single lookbook image for garment
consistency.

## Run it

```bash
cd onyx-supply
python3 -m http.server 4173
# open http://localhost:4173
```

Any static server works; the videos need HTTP (not file://) for range requests.

## What's inside

- **Hero** — 16:9 rooftop walk, scroll-scrubbed: the page pins for 4 viewport
  heights and your scroll position drives `video.currentTime`. Massive Anton
  type + live countdown to the next Friday 20:00 drop (rolls weekly).
- **Product grid** — three 1:1 turntable clips (heavyweight hoodie $180, cargo
  pants $210, chrome-accent puffer $340) that play on hover / tap, with size
  selectors, sold-out sizes that open a restock "Notify me" capture, and Add to
  Cart into a demo checkout drawer.
- **Fabric macro** — 16:9 close-up traveling across stitching, zipper teeth and
  the embossed logo, behind the "Built heavy. Cut clean." manifesto.
- **Extras** — marquee strips between sections, sticky cart with count badge,
  email capture section, film-grain overlay, acid-green (#c6ff00) on concrete
  gray and matte black, brutalist condensed type (Anton / Archivo).

## Media pipeline

`media-manifest.txt` maps filenames to generated-asset URLs. The GitHub Actions
workflow `.github/workflows/fetch-onyx-media.yml` downloads them into
`media/` and commits the bytes to the branch (the authoring sandbox couldn't
reach the CDN directly). All checkout/email flows are non-functional demo UI —
no data leaves the page.
