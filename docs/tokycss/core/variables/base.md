# Base Variables

## Screen Sizes

Reference breakpoints. Custom properties cannot be used inside `@media` conditions, so these are values to copy, not variables to reference in a query.

| Variable | Value |
|---|---|
| `--tk-screen-xs` | 320px |
| `--tk-screen-sm` | 640px |
| `--tk-screen-md` | 1024px |
| `--tk-screen-lg` | 1280px |
| `--tk-screen-xl` | 1440px |

```css
@media (min-width: 1024px) {
  /* --tk-screen-md is 1024px */
}
```

## Spacing System

A 4px-based spacing scale. The base unit is `--tk-size-unit` (4px). Each size is a multiple of this unit.

| Variable | Value | Variable | Value |
|---|---|---|---|
| `--tk-size-none` | none | `--tk-size-0` | 0 |
| `--tk-size-1` | 1px | `--tk-size-2` | 2px |
| `--tk-size-6` | 6px | `--tk-size-4` | 4px |
| `--tk-size-8` | 8px | `--tk-size-12` | 12px |
| `--tk-size-16` | 16px | `--tk-size-20` | 20px |
| `--tk-size-24` | 24px | `--tk-size-28` | 28px |
| `--tk-size-32` | 32px | `--tk-size-36` | 36px |
| `--tk-size-40` | 40px | `--tk-size-44` | 44px |
| `--tk-size-48` | 48px | `--tk-size-52` | 52px |
| `--tk-size-56` | 56px | `--tk-size-60` | 60px |
| `--tk-size-64` | 64px | `--tk-size-68` | 68px |
| `--tk-size-72` | 72px | `--tk-size-76` | 76px |
| `--tk-size-80` | 80px | `--tk-size-84` | 84px |
| `--tk-size-88` | 88px | `--tk-size-92` | 92px |
| `--tk-size-96` | 96px | `--tk-size-100` | 100px |

Use these for gaps, border-radius, padding, margin, and inset:

```css
.card {
  padding: var(--tk-size-24);
  gap: var(--tk-size-8);
  border-radius: var(--tk-size-8);
}
```

## Sizing, Values, and Properties

Percentage and viewport sizes, common CSS keywords, cursors, vertical alignment, and SVG values are native CSS. Tokens for them only rename the value you already know:

```css
.hero {
  width: 50%;
  min-height: 100vh;
}

.dimmed {
  cursor: not-allowed;
}
```
