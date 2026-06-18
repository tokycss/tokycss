# tokycss

A design token-first CSS framework for building custom user interfaces with consistency built in.

## Philosophy

**Tokens first. Components second. Utilities last.**

Toky CSS provides CSS variable tokens (colors, typography, spacing, layout, theming) as the foundation of your design system. Components consume tokens. Utilities exist for explicit control when needed — not as the primary way you build.

## Quick Start

Add to your HTML `<head>`:

```html
<link rel="stylesheet" href="styleguide.css" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/tokycss/tokycss@latest/dist/toky.css" crossorigin="anonymous" />
```

Your `styleguide.css` loads first and defines your project's colors, typography, and layout. Toky CSS provides everything else.

See the [installation guide](docs/tokycss/getting-started/installation.md) and [customization docs](docs/tokycss/customization/overview.md) for details.

## Features

- **Automatic OKLCH color scales** — Tints, shades, and alpha variants from one color
- **Theme system** — Light and dark mode via CSS `light-dark()` with `data-theme` overrides
- **Fluid typography** — Responsive type without media queries
- **Spacing system** — 4px-based systematic spacing
- **Layout foundations** — Flexible grid layout with breakout support
- **Sensible HTML defaults** — Improved reset, forms, tables, navigation, buttons
- **Semantic tokens** — Backgrounds, foregrounds, status colors, focus states
- **No JavaScript** — Pure CSS, no build step, no framework lock-in

## Documentation

- [Getting Started](docs/tokycss/getting-started/introduction.md)
- [Installation](docs/tokycss/getting-started/installation.md)
- [Customization](docs/tokycss/customization/overview.md)
- [Core Variables](docs/tokycss/core/variables/)
- [Core Styles](docs/tokycss/core/styles/)

## License

MIT
