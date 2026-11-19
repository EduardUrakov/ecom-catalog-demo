# Path Home — Catalogue (Unified Product Card System)

Static demo of a catalog page built on one product-card component that serves five
storefront modes: retail, marketplace, handmade, B2B wholesale and pre-order.
Storefront name: **Path Home** (Path ecosystem).

**Live demo:** https://eduardurakov.github.io/ecom-catalog-demo/

## What is inside

| Path | Contents |
|---|---|
| `index.html` | Language menu — 19 links into the same storefront. |
| `/<lang>/` | Server-rendered storefront: home, 4 departments, 16 subsections, 32 products. |
| `/<lang>/c/<dept>/<section>/`, `/<lang>/p/<sku>/` | Category and product pages, one file per address. |
| `assets/app.js` | One shared bundle (progressive enhancement), instead of 118 KB inlined into every page. |
| `assets/i18n.<lang>.js` | Dictionary of that language, so re-rendered blocks stay in the page language. |
| `catalog.html` | The original single-file demo — markup, styles and logic in one file. |
| `CATALOG.md` | Card anatomy, catalog tree, business decisions behind the structure. |
| `catalog.json`, `feed.xml` | Catalog in the `path-catalog/1.0` standard and a Merchant Center feed. |
| `sitemap.xml`, `llms.txt`, `robots.txt` | Machine layer. `robots.txt` currently disallows everything: the site is a closed contour until the customer approves the launch. Every page also carries `noindex`. |

Pages are built, not rendered by the browser: titles, prices, availability and links are in
the server response. Verify by opening a page with JavaScript disabled.

## Features to try

- 32 SKUs across 4 departments × 4 subsections, in 19 languages.
- One card component, five content modes, ten states, three sizes.
- Theme switcher: light / dark / high-contrast.
- Brand switcher — colors, radius and type come from CSS tokens only.
- Language menu in the header — 19 links to the same page, Arabic rendered right-to-left
  with Latin digits (`ar-u-nu-latn`), prices and dates formatted by `Intl` per language.
- Catalog dropdown (mega-menu) with live subsection counters.
- Configuration panel (gear icon) — turn departments and subsections on and off per client
  segment and niche. It is a demonstration tool: the storefront section set itself comes from
  `hub.config.js`, nothing is written to the browser.
- Keyboard: `Esc` closes overlays, `/` focuses search.

## Status of the translations

Interface translations are machine-made from the English source, the method the customer's
own rules allow (rules 04, question 17). They are not reviewed by native speakers yet;
`ha`, `am` and `sw` are the ones that need review first. Shared sections (footer, cookie
banner, consent, e-mail strings) come from the customer's `shared-sections-i18n` pack, 244
keys × 19 languages, which is itself a draft. Product model names, brand names and SKU codes
are not translated, by the same rules.

## Run locally

The static site is produced from the source project, not built inside this repository:

```bash
node build-catalog.js                 # single-file demo
node build-static.js --clean \
  --base=/ecom-catalog-demo \
  --public-url=https://eduardurakov.github.io/ecom-catalog-demo
node deploy-github.js --static --base=/ecom-catalog-demo
```

To look at `dist/` without deploying:

```bash
npx --yes http-server dist -p 8080
```

## Deployment

The `main` branch is published as-is by GitHub Pages through
`.github/workflows/pages.yml`. Any push to `main` redeploys automatically.

## License

MIT
