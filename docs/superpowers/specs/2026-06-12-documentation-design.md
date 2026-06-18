# TokyCSS Documentation Design

> **Status:** Approved
> **Date:** 2026-06-12

## Goal

Write clear, articulate documentation for the TokyCSS framework organized as separate Markdown files under `docs/`.

## Architecture

TokyCSS is a **Design System-first CSS Framework**. It uses element selectors for automatic styling, complemented by utility and layout classes for explicit control. Delivered via a single jsDelivr CDN link. Users customize through `styleguide.css`.

Documentation mirrors the conceptual layers: getting started, customization, and a reference section covering variables (design tokens) and styles.

## Naming Conventions

The framework follows two consistent variable patterns:

- **Scale values** — ordered magnitudes along a spectrum: `--tk-<category>-<scale>`
  - e.g. `--tk-duration-xs`, `--tk-size-24`, `--tk-font-weight-700`, `--tk-color-primary-5xlight`
  - Scale modifiers: `2x` (smallest/fastest) → `xs` → `sm` → `md` → `lg` → `xl` → `2xl` → `3xl`
  - Color modifiers: `5xlight` → `4xlight` → ... → `1xlight` → base → `1xdark` → ... → `5xdark`, `1a`–`10a` for alpha

- **Semantic/named values** — named roles or things: `--tk-<category>-<name>`
  - e.g. `--tk-font-body`, `--tk-ease-elastic`, `--tk-color-primary`

## Documentation Style

- Use easy-to-understand English without diluting CSS terminology
- Progressive — each page builds on previous concepts
- Include code examples, tips, notes, and warnings where helpful
- Document **what users need**: not internal engine mechanics, only the variables and classes they use

## File Structure

```
docs/
  getting-started/
    installation.md         — CDN link, styleguide.css setup, basic boilerplate
  customization/
    styleguide.md           — How to customize via styleguide.css
  core/
    variables/
      colors.md             — Brand colors, theme, semantic (success/warning/info/error)
                              with tints, shades, alpha variants, shadows
      base.md               — Core spacing sizes, percentage/vw/vh sizing, 4px spacing system
      layout.md             — Grid engine overview (configure via styleguide.css), lane classes
      border.md             — Border radius, widths, styles, outline
      effects.md            — Filters (blur, brightness, contrast, etc.), opacity scale
      typography.md         — Usable font/type variables (not fluid engine internals)
      animation.md          — Durations, easings, transitions
      theme.md              — Semantic tokens, prefers-color-scheme, data-theme overrides
    styles/
      reset.md              — Normalization, focus, selection, scrollbar, print/reduced-motion
      typography.md         — h1-h6, p, links, strong, em, small, code, kbd, pre, blockquote, lists, hr, details, figure
      forms.md              — Labels, inputs, textareas, selects, checkboxes, radios, range, color, file, progress, fieldset
      components.md         — Buttons, tables, dialog, nav
      layout.md             — Header, main, section, footer, aside + .layout--grid system
      utilities.md          — btn--sm/md/lg, aria-busy, aria-disabled, data-status, data-sr-only
```

## Design Per File

### getting-started/installation.md
- What TokyCSS is: Design System-first CSS Framework
- Browser support philosophy: Baseline Widely Available, with a few intentional exceptions documented transparently
- Single jsDelivr CDN link in `<head>`
- `styleguide.css` as the user's customization layer
- Basic HTML boilerplate with both linked
- Brief "Hello World" example

### customization/styleguide.md
- `styleguide.css` is the single file users edit
- Link to Huemint palette generator for visual palette picking
- Setting brand colors: `--tk-color-primary`, `--tk-color-secondary`, `--tk-color-accent`
- Theme hue tinting via `--tk-color-theme`
- Typography font stack overrides (`--tk-font-sans`, `--tk-font-serif`, `--tk-font-mono`)
- Page gutter and content width
- Fluid scale bounds
- Full minimal example

### core/variables/colors.md
- Brand color variables (primary, secondary, accent)
- Theme color scale
- Semantic colors: success, warning, error, info
- Tint/shade/alpha variants for all of the above
- Shadow variables (xs through 2xl)

### core/variables/base.md
- Screen size breakpoints (sm, md, lg, xl, 2xl)
- 4px spacing system — used for gaps, border-radius, padding/margin, inset
- Common values (auto, none, normal, etc.)
- Percentage/vw/vh sizing for widths, heights, degrees
- Cursor, alignment, table, SVG properties

### core/variables/layout.md
- Grid engine explanation: how the named-grid-line system works
- Configuring lanes via `styleguide.css` (`--tk-content-width`, `--tk-content-fill-width`, `--tk-page-gutter`)
- Position, display, overflow, flexbox, grid variables
- Lane classes: `.layout--grid`, `.layout--main`, `.layout--fill`, `.layout--full`, and cross-lane utilities

### core/variables/border.md
- Border radius scale (0 through full)
- Border widths and styles
- Outline properties

### core/variables/effects.md
- Filter system: blur, brightness, contrast, grayscale, hue-rotate, invert, saturate, sepia
- Opacity scale

### core/variables/typography.md
- Fluid type scale variables (xs through 9xl) — only the variables, not the engine
- Font weights, line heights, letter spacing
- Text decoration, transform, alignment
- List style, text direction, writing mode
- Background properties

### core/variables/animation.md
- Duration values (2x through 3xl)
- Delay values
- Easing functions (standard + expressive)
- Preset animations (spin, ping, pulse, bounce, etc.)
- Transition system (duration presets + common transitions)
- Note mapping inconsistencies if any remain

### core/variables/theme.md
- Semantic tokens concept: backgrounds use tints, foregrounds use shades
- `@media (prefers-color-scheme: dark)` for automatic dark mode
- All background and foreground variables
- Status background/foreground tokens
- `data-theme="light"` and `data-theme="dark"` overrides

### core/styles/reset.md
- Box-sizing, font smoothing, text-rendering
- Body defaults (font, color, background, max-width, min-height)
- Heading font/letter-spacing
- Media element defaults
- `data-img-fit` behavior
- Focus-visible focus ring
- Selection styling
- Scrollbar styling
- Print and reduced-motion quirks

### core/styles/typography.md
- Heading hierarchy (h1-h6) with sizes, weights, line-heights
- Paragraphs and adjacent heading+paragraph sizing
- Inline semantics: strong, em, small, code, kbd, samp, mark
- Links with hover states
- Pre-formatted blocks
- Blockquotes with cite
- Lists (ul/ol in article/section/main)
- Horizontal rules
- Details/summary with animated disclosure marker
- Figure/figcaption

### core/styles/forms.md
- Labels (block display, sizing, required asterisk)
- Text-like inputs, textareas, selects (with custom chevron)
- Focus and hover states
- Disabled state
- Checkboxes and radios (custom styled, checked states)
- Range input (custom slider thumb)
- Color input
- File input with styled button
- Progress bar
- Fieldset/legend

### core/styles/components.md
- Buttons: base style, active scale, disabled state
- Tables: full-width, thead styling, th/td, tbody hover, caption
- Dialog: centered modal, backdrop blur, entry animation
- Nav: horizontal flex, link hover, aria-current active state

### core/styles/layout.md
- Semantic element defaults: header (flex nav), main (centered), section, footer, aside
- `.layout--grid` system: what it is, how to apply it
- Lane classes: `.layout--main`, `.layout--fill`, `.layout--full`
- Advanced cross-lane utilities

### core/styles/utilities.md
- Button size modifiers: `.btn--sm`, `.btn--md`, `.btn--lg`
- `[aria-busy="true"]` — progress indicator
- `[aria-disabled="true"]` — disabled state
- `[data-status]` — success, warning, danger/error, info
- `[data-sr-only]` — screen reader only

## Known Issues with Suggested Fixes

These are noted in documentation but not yet fixed:

### 1. ~~`data-theme` overrides are incomplete~~ **(Resolved)**

**Fix:** Replaced `@media (prefers-color-scheme: dark)` with CSS `light-dark()` in every semantic token declaration. Now `[data-theme]` blocks work correctly — `light-dark()` respects the `color-scheme` property, so setting `color-scheme: dark` on `[data-theme="dark"]` properly switches all bg/fg tokens.

### 2. ~~`--tk-focus-ring-alt` references undefined `--tk-bg-surface`~~ **(Resolved)**

**Fix:** Removed `--tk-focus-ring-alt` and its undefined `--tk-bg-surface` dependency from `theme.css`. The variable was never consumed anywhere in the codebase.

### 3. ~~`--tk-anim-default-easing` defined but unused~~ **(Resolved)**

**Fix:** Removed the dead `--tk-anim-default-easing` declaration from `animation.css`. All style files use `--tk-ease` directly.

### 4. Non-widely-available CSS in reset

**Problem:** `reset.css` uses `hanging-punctuation: first last` and `text-wrap: pretty`. These are not Baseline Widely Available.

**Suggested fix:** For `hanging-punctuation`, wrap in `@supports`:
```css
@supports (hanging-punctuation: first last) {
  html { hanging-punctuation: first last; }
}
```
For `text-wrap: pretty`, the same pattern or fallback to `text-wrap: balance` then `text-wrap: pretty`:
```css
p, span { overflow-wrap: break-word; text-wrap: balance; }
@supports (text-wrap: pretty) {
  p, span { text-wrap: pretty; }
}
```
