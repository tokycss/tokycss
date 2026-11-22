# Layout Variables

## Grid Layout Engine

TokyCSS uses a CSS Grid system with named grid lines to create content-aware page layouts. The grid defines three horizontal lanes:

- **Main** — the primary readable content area (default 80ch)
- **Fill** — a wider breakout area extending beyond main
- **Full** — edge-to-edge, spanning the whole viewport

Named grid lines mark the boundaries:

```
| full-start | gutter | fill-start | breakout | main-start | content | main-end | breakout | fill-end | gutter | full-end |
```

All direct children of `.layout--grid` default to the **main** lane. Override with lane classes (see [Layout Styles](../styles/layout.md) for the class system).

Configure the lane widths in `styleguide.css`:

```css
@layer styleguide {
  :root {
    --tk-content-width: 80ch;             /* Main lane width */
    --tk-breakout-width: 90ch;            /* Fill lane width */
    --tk-page-gutter: var(--tk-size-20);  /* Side gutters */
  }
}
```

The grid engine itself is internal and prefixed `--_tk-layout-*`. Configure it through the tokens above, not by editing the engine.

## Z-Index

A semantic layering scale. The numbers matter less than the order, and the token says what the layer is for.

| Variable | Value | Use |
|---|---|---|
| `--tk-z-index-auto` | auto | No stacking |
| `--tk-z-index-xs` | 1 | In-flow nudges |
| `--tk-z-index-sm` | 10 | Sticky headers |
| `--tk-z-index-md` | 100 | Dropdowns |
| `--tk-z-index-lg` | 1000 | Dialogs |
| `--tk-z-index-xl` | 10000 | Toasts |

## Aspect Ratios

| Variable | Value |
|---|---|
| `--tk-square` | 1 / 1 |
| `--tk-video` | 16 / 9 |
| `--tk-portrait` | 3 / 4 |
| `--tk-landscape` | 4 / 3 |
| `--tk-widescreen` | 21 / 9 |
| `--tk-golden` | 1.618 / 1 |

```css
.thumbnail {
  aspect-ratio: var(--tk-video);
}
```

## Position, Display, Overflow, Flexbox, Grid, Gap

These are native CSS values. Use them directly — `display: flex` is shorter than a token and needs no lookup:

```css
.row {
  display: flex;
  gap: 8px;
  align-items: center;
  justify-content: space-between;
}

.panel {
  position: absolute;
  overflow: hidden;
}
```

Grid alignment values (`auto-fit`, `auto-fill`, `start`, `center`, `stretch`, `space-between`) are likewise native.
