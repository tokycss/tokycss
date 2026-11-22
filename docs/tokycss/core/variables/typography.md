# Typography Variables

## Fluid Type Scale

TokyCSS uses a fluid type scale that automatically adjusts between viewport sizes. Variables are labeled by size — from meta text to massive display type.

| Variable | Min | Max | Ideal for |
|---|---|---|---|
| `--tk-text-xs` | 0.75rem (12px) | 0.875rem (14px) | Meta, fine print, tooltips |
| `--tk-text-sm` | 0.875rem (14px) | 1rem (16px) | Captions, small buttons |
| `--tk-text-md` | 1rem (16px) | 1.125rem (18px) | Body text, inputs |
| `--tk-text-lg` | 1.125rem (18px) | 1.25rem (20px) | Lead text, large buttons |
| `--tk-text-xl` | 1.25rem (20px) | 1.5rem (24px) | H5, card titles |
| `--tk-text-2xl` | 1.5rem (24px) | 2rem (32px) | H4, section titles |
| `--tk-text-3xl` | 1.875rem (30px) | 2.5rem (40px) | H3, article titles |
| `--tk-text-4xl` | 2.25rem (36px) | 3rem (48px) | H2, page headers |
| `--tk-text-5xl` | 3rem (48px) | 4rem (64px) | H1, page titles |
| `--tk-text-6xl` | 3.75rem (60px) | 5rem (80px) | Hero text |
| `--tk-text-7xl` | 4.5rem (72px) | 6rem (96px) | Large hero, stats |
| `--tk-text-8xl` | 6rem (96px) | 8rem (128px) | Creative typography |
| `--tk-text-9xl` | 8rem (128px) | 10rem (160px) | Oversized display |

```css
h1 { font-size: var(--tk-text-5xl); }
small { font-size: var(--tk-text-xs); }
```

Each step also exposes its endpoints as `--tk-text-<size>-min` and `--tk-text-<size>-max` if you need to tune one step. The fluid engine itself (`--_tk-fluid-*`) is internal.

## Line Heights

| Variable | Value | Best for |
|---|---|---|
| `--tk-line-height-xs` | 0.55 | Display headings |
| `--tk-line-height-sm` | 1.1 | Headings |
| `--tk-line-height-md` | 1.25 | Tight text |
| `--tk-line-height-lg` | 1.5 | Body text |
| `--tk-line-height-xl` | 1.625 | Relaxed reading |

## Letter Spacing

| Variable | Value |
|---|---|
| `--tk-letter-spacing-xs` | -0.05em |
| `--tk-letter-spacing-sm` | -0.025em |
| `--tk-letter-spacing-md` | 0em (normal) |
| `--tk-letter-spacing-lg` | 0.025em |
| `--tk-letter-spacing-xl` | 0.1em |

## Font Weights, Stretch, Style, Variants

These are native CSS values. Write them directly:

```css
.strong {
  font-weight: 700;
}

.caps {
  font-variant-caps: small-caps;
}

.narrow {
  font-stretch: condensed;
}
```

## Text Decoration, Transform, Alignment, and Wrapping

Also native. Use the CSS keyword:

```css
.link {
  text-decoration: underline wavy 2px;
  text-underline-offset: 0.15em;
}

.label {
  text-transform: uppercase;
  text-align: left;
  text-wrap: balance;
}

.list {
  list-style: disc;
}

.no-select {
  user-select: none;
}
```
