# E-commerce Catalog Demo — Unified Product Card System

Static demo of a catalog page built on one product-card component that serves five
storefront modes: retail, marketplace, handmade, B2B wholesale and pre-order.

**Live demo:** https://eduardurakov.github.io/ecom-catalog-demo/

## What is inside

| File | Contents |
|---|---|
| `catalog.html` | The demo page. Self-contained: markup, styles and logic in one file. |
| `index.html` | Byte-identical copy of `catalog.html`, so the repository root opens the catalog. |
| `CATALOG.md` | Card anatomy, catalog tree, business decisions behind the structure. |

## Features to try

- 32 SKUs across 4 departments × 4 subsections.
- One card component, five content modes, ten states, three sizes.
- Theme switcher: light / dark / high-contrast.
- Brand switcher — colors, radius and type come from CSS tokens only.
- `RU / EN` toggle — the whole interface, including card copy, switches language.
- Catalog dropdown (mega-menu) with live subsection counters.
- Configuration panel (gear icon) — turn departments and subsections on and off
  per client segment and niche. Selection persists in `localStorage`.
- Keyboard: `Esc` closes overlays, `/` focuses search.

## Run locally

No build step, no dependencies — open the file in a browser:

```bash
npx --yes http-server gh-pages -p 8080
# then open http://localhost:8080/catalog.html
```

## Deployment

The `main` branch is published as-is by GitHub Pages through
`.github/workflows/pages.yml`. Any push to `main` redeploys automatically.

## License

MIT
