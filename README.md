# Markfluent brand assets

Logo, colour and typography for Markfluent. Everything is vector; the wordmark is Satoshi 700
converted to outlines, so no font files are needed to render any asset here.

Open `preview.html` in a browser to see the full set (colour swatches, lockups, icon sizes, social
card, usage rules). The preview picks up Satoshi from the website's `/fonts/` when served next to the
site and falls back to the system sans otherwise; the assets themselves are unaffected.

## Colour

| Token | Hex | RGB | Use |
| --- | --- | --- | --- |
| Primary purple | `#7E5EFF` | 126, 94, 255 | Buttons, highlights, key headings, accent icons |
| Ink | `#2D1E6B` | 45, 30, 107 | Headlines, body copy, wordmark |
| Canvas | `#FAFAFF` | 250, 250, 255 | Page background, sections, whitespace |
| Lavender | `#EFECFF` | 239, 236, 255 | Cards, hover states, section separators |

White (`#FFFFFF`) is the only additional colour, used for the reverse lockup on ink.

## Contents

```
tokens.json                          colours and type as JSON
brand.css                            the same as CSS custom properties + .mf-logo
preview.html                         human-readable brand sheet
svg/
  markfluent-logo-horizontal.svg          primary lockup
  markfluent-logo-horizontal-reverse.svg  white wordmark, purple mark, for ink backgrounds
  markfluent-logo-stacked.svg             vertical lockup
  markfluent-logo-stacked-reverse.svg
  markfluent-wordmark.svg                 Markfluent, ink
  markfluent-wordmark-white.svg
  markfluent-icon.svg                     mark alone, purple, transparent
  markfluent-icon-mono-ink.svg
  markfluent-icon-mono-white.svg
  markfluent-favicon.svg                  mark on lavender rounded tile
  markfluent-social-card.svg              open graph card, 1200x630
png/
  icon-1024.png icon-512.png icon-192.png app icons
  apple-touch-icon.png                    180x180
  favicon-32.png favicon-16.png favicon.ico
  social-card-1200x630.png
  logo-horizontal-1200.png logo-stacked-800.png
```

## Using it on a site

`brand.css` exposes `--mf-purple`, `--mf-purple-rgb`, `--mf-ink`, `--mf-ink-rgb`, `--mf-canvas`,
`--mf-lavender`, `--mf-white`, `--mf-font`, `--mf-radius` and `--mf-logo-height`, plus a `.mf-logo`
wrapper that sizes a lockup by height:

```html
<link rel="stylesheet" href="/brand/brand.css">

<a class="mf-logo" href="/" style="--mf-logo-height:32px">
  <img src="/brand/svg/markfluent-logo-horizontal.svg" alt="Markfluent">
</a>
```

Favicon and social tags:

```html
<link rel="icon" href="/brand/svg/markfluent-favicon.svg" type="image/svg+xml">
<link rel="alternate icon" href="/brand/png/favicon.ico" sizes="32x32">
<link rel="apple-touch-icon" href="/brand/png/apple-touch-icon.png">
<meta property="og:image" content="/brand/png/social-card-1200x630.png">
```

The paths above assume this repo's contents are served from `/brand/` (the site keeps a copy at
`public/brand/`). Any static host or raw URL works as long as the folder layout is preserved.

## Rules

- Clear space on every side: at least the height of the funnel mark.
- Minimum sizes: horizontal lockup 120 px wide, stacked 96 px wide, icon 16 px (use the favicon tile
  at 16 px).
- Do not stretch, rotate, outline, add shadows or gradients, or re-type the wordmark in another font.
- Purple mark with ink wordmark on light surfaces; white wordmark with purple mark on ink. Nothing else.

## Regenerating

The mark is hand-authored on a 64-unit grid: a funnel plus a rising zigzag arrow with a 6.7 unit
stroke and a chunky rounded arrowhead. The wordmark is Satoshi 700 outlined at 1000 units per em with
-8/1000 tracking. Edit the SVG directly, then re-export the PNGs at the sizes listed above so the
raster and vector sets stay in step.
