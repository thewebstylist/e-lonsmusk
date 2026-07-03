# ONYX SUPPLY — Midnight Drop

Cinematic e-commerce concept site for a fictional premium streetwear label. One
self-contained HTML file plus AI-generated footage (Seedance 2.0 via Higgsfield,
std mode, 1080p, silent), all anchored to a single lookbook image for garment
consistency.

## Run it

```bash
cd onyx-supply
npx http-server -p 4173
# open http://localhost:4173
```

Use a server that supports HTTP Range requests (http-server, serve, nginx, any
CDN). Plain `python3 -m http.server` lacks Range support, which breaks video
seeking — the hero scroll-scrub will appear frozen or jumpy.

## What's inside

- **Hero** — 16:9 rooftop walk, scroll-scrubbed: the page pins for 4 viewport
  heights and your scroll position drives `video.currentTime`. Massive Anton
  type + live countdown to the next Friday 20:00 drop (rolls weekly). The hero
  plays from `hero-scrub.mp4/.webm` — all-intra re-encodes (every frame a
  keyframe) so seeks land on every frame instead of jumping between sparse
  keyframes; `hero.mp4` is the original master.
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
