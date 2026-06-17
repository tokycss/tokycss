# Variable Naming Consolidation — Design Spec

## Goal

Standardize all CSS custom property groups that use t-shirt-size naming to a consistent 5-step scale (`*-xs`, `*-sm`, `*-md`, `*-lg`, `*-xl`) with optional special steps (`*-0`, `*-full`, `*-none`) outside the 5-step count. Eliminate `*-2xs` and `*-base` from the framework entirely. Convert non-t-shirt scales (effects, opacity) to the same convention.

## Files Affected

| File | Action |
|------|--------|
| `src/core/variables/border.css` | Rename/remove variables, keep specials |
| `src/core/variables/animation.css` | Condense to 5 steps, keep easing/presets |
| `src/core/variables/base.css` | Breakpoints relabeled, stroke condensed, spacing micro values cleaned |
| `src/core/variables/typography.css` | All t-shirt groups condensed to 5 steps |
| `src/core/variables/effects.css` | Convert filter/opacity to t-shirt naming and move shadows here |
| `src/core/variables/colors.css` | Remove `--tk-color-shadow-*`, keep `--tk-color-shadow` base color |
| `src/core/styles/*.css` | Update variable references in consumers |

---

## 1. Border, Radius, Outline (`border.css`)

### Border-radius
```
--tk-radius-0:    0px         (kept, not counted)
--tk-radius-2xs → REMOVED     (was 1px)
--tk-radius-xs  → kept        2px
--tk-radius-sm  → kept        4px
--tk-radius-md  → kept        8px
--tk-radius-lg  → kept        12px
--tk-radius-xl  → kept        16px
--tk-radius-2xl → REMOVED     (was 20px)
--tk-radius-3xl → REMOVED     (was 24px)
--tk-radius-full: 9999px      (kept, not counted)
```

### Border-width
```
--tk-border-0:   0px           (kept, not counted)
--tk-border-2xs → --tk-border-xs    1px
--tk-border-xs  → --tk-border-sm    2px
--tk-border-sm  → --tk-border-md    4px
--tk-border-md  → --tk-border-lg    8px
--tk-border-lg  → REMOVED           (was 12px)
--tk-border-xl  → kept              16px
--tk-border-2xl → REMOVED           (was 20px)
--tk-border-3xl → REMOVED           (was 24px)
```

### Outline-width
Same shift as border-width:
```
--tk-outline-0:     0px         (kept, not counted)
--tk-outline-2xs  → --tk-outline-xs    1px
--tk-outline-xs   → --tk-outline-sm    2px
--tk-outline-sm   → --tk-outline-md    4px
--tk-outline-md   → --tk-outline-lg    8px
--tk-outline-lg   → REMOVED
--tk-outline-xl   → kept               16px
--tk-outline-2xl  → REMOVED
--tk-outline-3xl  → REMOVED
```

### Border styles / Outline styles
Unchanged (fixed/locked values).

---

## 2. Animation (`animation.css`)

### Duration
```
--tk-duration-2x  → --tk-duration-xs    0.1s
--tk-duration-xs  → --tk-duration-sm    0.35s
--tk-duration-sm  → REMOVED             (was 0.5s)
--tk-duration-md  → kept                0.8s
--tk-duration-lg  → kept                1.5s
--tk-duration-xl  → kept                3s
--tk-duration-2xl → REMOVED             (was 4s)
--tk-duration-3xl → REMOVED             (was 8s)
```

### Delay
```
--tk-delay-2x  → --tk-delay-xs    0.05s
--tk-delay-xs  → --tk-delay-sm    0.15s
--tk-delay-sm  → REMOVED          (was 0.2s)
--tk-delay-md  → kept             0.4s
--tk-delay-lg  → kept             0.7s
--tk-delay-xl  → kept             1.5s
--tk-delay-2xl → REMOVED          (was 1.2s)
--tk-delay-3xl → REMOVED          (was 2s)
```

### Transition duration
```
--tk-transition-2x  → --tk-transition-xs    150ms
--tk-transition-xs  → --tk-transition-sm    225ms
--tk-transition-sm  → REMOVED               (was 250ms)
--tk-transition-md  → kept                  300ms
--tk-transition-lg  → kept                  375ms
--tk-transition-xl  → kept                  450ms
--tk-transition-2xl → REMOVED               (was 450ms)
--tk-transition-3xl → REMOVED               (was 500ms)
```

### Transition presets
- Remove `--tk-transition-all-2x`, `--tk-transition-all-2xl`, `--tk-transition-all-3xl`
- Rename `--tk-transition-all-xs` → keep (value becomes 150ms)
- Rename `--tk-transition-all-sm` → keep (value becomes 225ms)
- Rename `--tk-transition-all-lg` → keep (value becomes 375ms)
- Rename `--tk-transition-all-xl` → keep (value becomes 450ms)
- Keep `--tk-transition-all` (0.4s), `--tk-transition-all-md` (0.3s)

### Easing / Animation presets / Animation defaults
Unchanged.

---

## 3. SVG Stroke (`base.css`)

```
--tk-stroke-0:   0px          (kept, not counted)
--tk-stroke-2x → --tk-stroke-xs    1px
--tk-stroke-xs → --tk-stroke-sm    2px
--tk-stroke-sm → --tk-stroke-md    4px
--tk-stroke-md → --tk-stroke-lg    8px
--tk-stroke-lg → REMOVED           (was 12px)
--tk-stroke-xl → kept              16px
--tk-stroke-2xl → REMOVED
--tk-stroke-3xl → REMOVED
```

---

## 4. Breakpoints (`base.css`)

Relabeling — values shift up one step:

```
--tk-screen-xs: 480px    (was --tk-screen-sm)
--tk-screen-sm: 768px    (was --tk-screen-md)
--tk-screen-md: 1024px   (was --tk-screen-lg)
--tk-screen-lg: 1280px   (was --tk-screen-xl)
--tk-screen-xl: 1440px   (was --tk-screen-2xl)
```

---

## 5. Spacing — Special Values (`base.css`)

Replace current micro values:

```css
--tk-size-none: var(--tk-value-none);
--tk-size-0: var(--tk-value-0);
--tk-size-1: 1px;
--tk-size-2: 2px;
--tk-size-6: 6px;
```

`--tk-size-2xs` (0.5px) removed. 4px-scale untouched.

T-shirt aliases added (point to existing 4px-scale values):
```
--tk-size-xs → --tk-size-4     4px
--tk-size-sm → --tk-size-8     8px
--tk-size-md → --tk-size-16    16px
--tk-size-lg → --tk-size-32    32px
--tk-size-xl → --tk-size-64    64px
```

---

## 6. Typography — Condensed Groups (`typography.css`)

### Line-height
```
--tk-line-height-2xs → --tk-line-height-xs    0.55
--tk-line-height-xs  → --tk-line-height-sm    1
--tk-line-height-sm  → --tk-line-height-md    1.25
--tk-line-height-md  → --tk-line-height-lg    1.5
--tk-line-height-lg  → --tk-line-height-xl    1.625
--tk-line-height-xl  → REMOVED                (was 2)
--tk-line-height-2xl → REMOVED                (was 0.75rem)
--tk-line-height-3xl → REMOVED                (was 1rem)
```

### Letter-spacing
Fix inverted bug (xs was tighter than 2xs):
```
--tk-letter-spacing-2xs  → REMOVED           (was -0.05em)
--tk-letter-spacing-xs   → value fixed        -0.05em (was -0.1em)
--tk-letter-spacing-sm   → kept               -0.025em
--tk-letter-spacing-md   → kept               0em
--tk-letter-spacing-lg   → kept               0.025em
--tk-letter-spacing-xl   → value bumped       0.1em (was -2xl value)
--tk-letter-spacing-2xl  → REMOVED            (was 0.1em)
--tk-letter-spacing-3xl  → REMOVED            (was 0.2em)
```

### Text-shadow
```
--tk-text-shadow-none  → kept        none
--tk-text-shadow-2xs   → REMOVED     (was 0.5px)
--tk-text-shadow-xs    → kept        1px 1px 2px rgba(0,0,0,0.1)
--tk-text-shadow-sm    → kept        2px 2px 4px rgba(0,0,0,0.1)
--tk-text-shadow-md    → kept        4px 4px 6px rgba(0,0,0,0.1)
--tk-text-shadow-lg    → kept        6px 6px 8px rgba(0,0,0,0.15)
--tk-text-shadow-xl    → kept        8px 8px 10px rgba(0,0,0,0.15)
--tk-text-shadow-2xl   → REMOVED     (was 10px)
--tk-text-shadow-3xl   → REMOVED     (was 12px)
```

### Text-stroke
```
--tk-text-stroke-2xs → --tk-text-stroke-xs    1px
--tk-text-stroke-xs  → --tk-text-stroke-sm    2px
--tk-text-stroke-sm  → --tk-text-stroke-md    4px
--tk-text-stroke-md  → --tk-text-stroke-lg    8px
--tk-text-stroke-xl  → kept                   16px
--tk-text-stroke-2xl → REMOVED                (was 20px)
--tk-text-stroke-3xl → REMOVED                (was 24px)
```

### Indent
```
--tk-indent-0     → kept             0           (not counted)
--tk-indent-2xs   → REMOVED          (was 0.0325rem)
--tk-indent-xs    → kept             0.0625rem
--tk-indent-sm    → kept             0.25rem
--tk-indent-md    → kept             0.5rem
--tk-indent-lg    → kept             1rem
--tk-indent-xl    → kept             2rem
--tk-indent-2xl   → REMOVED          (was 2.5rem)
--tk-indent-3xl   → REMOVED          (was 3rem)
```

### Underline offset
```
--tk-text-underline-offset-auto  → kept                    auto    (not counted)
--tk-text-underline-offset-0     → kept                    0       (not counted)
--tk-text-underline-offset-2xs   → REMOVED                 (was 0.5px)
--tk-text-underline-offset-xs    → kept                    1px
--tk-text-underline-offset-sm    → kept                    2px
--tk-text-underline-offset-md    → value changed 0.15em → 4px
--tk-text-underline-offset-lg    → kept                    8px
--tk-text-underline-offset-xl    → kept                    10px
--tk-text-underline-offset-2xl   → REMOVED                 (was 12px)
--tk-text-underline-offset-3xl   → REMOVED                 (was 14px)
```

### Underline thickness
```
--tk-text-underline-auto      → kept        auto        (not counted)
--tk-text-underline-from-font → kept        from-font   (not counted)
--tk-text-underline-0         → kept        0px         (not counted)
--tk-text-underline-2xs       → --tk-text-underline-xs     1px
--tk-text-underline-xs        → --tk-text-underline-sm     2px
--tk-text-underline-sm        → --tk-text-underline-md     4px
--tk-text-underline-md        → --tk-text-underline-lg     6px
--tk-text-underline-lg        → --tk-text-underline-xl     8px
--tk-text-underline-xl        → REMOVED                    (was 10px)
--tk-text-underline-2xl       → REMOVED                    (was 12px)
--tk-text-underline-3xl       → REMOVED                    (was 14px)
```

---

## 7. Effects & Opacity (`effects.css`)

### Blur
| Name | Value | Source |
|------|-------|--------|
| `--tk-filter-blur-0` | blur(0px) | kept |
| `--tk-filter-blur-xs` | blur(1px) | was `-1x` |
| `--tk-filter-blur-sm` | blur(2px) | was `-2x` |
| `--tk-filter-blur-md` | blur(4px) | was `-3x` |
| `--tk-filter-blur-lg` | blur(8px) | was `-4x` |
| `--tk-filter-blur-xl` | blur(16px) | was `-6x` |
| `--tk-filter-blur-full` | blur(100px) | kept |

### Brightness
| Name | Value | Source |
|------|-------|--------|
| `--tk-filter-brightness-0` | brightness(1) | kept |
| `--tk-filter-brightness-xs` | brightness(1.1) | was `-1x` |
| `--tk-filter-brightness-sm` | brightness(1.2) | was `-2x` |
| `--tk-filter-brightness-md` | brightness(1.5) | was `-4x` |
| `--tk-filter-brightness-lg` | brightness(2) | was `-6x` |
| `--tk-filter-brightness-xl` | brightness(3) | was `-8x` |
| `--tk-filter-brightness-full` | brightness(5) | kept |

### Contrast
| Name | Value | Source |
|------|-------|--------|
| `--tk-filter-contrast-0` | contrast(1) | kept |
| `--tk-filter-contrast-xs` | contrast(1.05) | was `-1x` |
| `--tk-filter-contrast-sm` | contrast(1.1) | was `-2x` |
| `--tk-filter-contrast-md` | contrast(1.35) | was `-4x` |
| `--tk-filter-contrast-lg` | contrast(1.75) | was `-6x` |
| `--tk-filter-contrast-xl` | contrast(2.5) | was `-8x` |
| `--tk-filter-contrast-full` | contrast(4) | kept |

### Grayscale / Invert / Sepia
| Name | Value | Notes |
|------|-------|-------|
| `--tk-filter-{type}-0` | {type}(0%) | kept |
| `--tk-filter-{type}-xs` | {type}(15%) | interpolated |
| `--tk-filter-{type}-sm` | {type}(30%) | interpolated |
| `--tk-filter-{type}-md` | {type}(50%) | was `-5x` |
| `--tk-filter-{type}-lg` | {type}(70%) | interpolated |
| `--tk-filter-{type}-xl` | {type}(85%) | interpolated |
| `--tk-filter-{type}-full` | {type}(100%) | kept |

### Hue-rotate
| Name | Value | Source |
|------|-------|--------|
| `--tk-filter-hue-rotate-0` | hue-rotate(0deg) | kept |
| `--tk-filter-hue-rotate-xs` | hue-rotate(30deg) | was `-2x` |
| `--tk-filter-hue-rotate-sm` | hue-rotate(60deg) | was `-4x` |
| `--tk-filter-hue-rotate-md` | hue-rotate(120deg) | was `-6x` |
| `--tk-filter-hue-rotate-lg` | hue-rotate(180deg) | was `-7x` |
| `--tk-filter-hue-rotate-xl` | hue-rotate(270deg) | was `-8x` (rounded) |
| `--tk-filter-hue-rotate-full` | hue-rotate(360deg) | kept |

### Saturate
| Name | Value | Source |
|------|-------|--------|
| `--tk-filter-saturate-0` | saturate(0) | kept |
| `--tk-filter-saturate-xs` | saturate(0.25) | was `-1x` |
| `--tk-filter-saturate-sm` | saturate(0.5) | was `-2x` |
| `--tk-filter-saturate-md` | saturate(1) | was `-4x` |
| `--tk-filter-saturate-lg` | saturate(2) | was `-6x` |
| `--tk-filter-saturate-xl` | saturate(4) | was `-8x` |
| `--tk-filter-saturate-full` | saturate(8) | kept |

### Opacity
| Name | Value | Notes |
|------|-------|-------|
| `--tk-opacity-0` | 0 | new |
| `--tk-opacity-xs` | 0.1 | was `-1x` |
| `--tk-opacity-sm` | 0.25 | interpolated |
| `--tk-opacity-md` | 0.5 | was `-5x` |
| `--tk-opacity-lg` | 0.75 | interpolated |
| `--tk-opacity-xl` | 0.9 | was `-9x` |
| `--tk-opacity-full` | 1 | kept |

---

## 8. Shadows (moved to `effects.css`)

`--tk-color-shadow` (base color) stays in `colors.css`.

Shadow variables move to `effects.css` and rename:
```
--tk-color-shadow-xs → --tk-shadow-xs    (value kept)
--tk-color-shadow-sm → --tk-shadow-sm    (value kept)
--tk-color-shadow-md → --tk-shadow-md    (value kept)
--tk-color-shadow-lg → --tk-shadow-lg    (value kept)
--tk-color-shadow-xl → --tk-shadow-xl    (value kept)
--tk-color-shadow-2xl → REMOVED
```

---

## 9. Text sizes (`typography.css`)

Untouched. Current `--tk-text-xs` through `--tk-text-9xl` remain as-is.

---

## 10. Styles Sync (`src/core/styles/*.css`)

### `typography.css`
- `--tk-radius-sm` → kept (value unchanged)
- `--tk-line-height-xs` → `--tk-line-height-sm` (value: 1)
- `--tk-line-height-sm` → `--tk-line-height-md` (value: 1.25)
- `--tk-line-height-md` → `--tk-line-height-lg` (value: 1.5)
- `--tk-duration-xs` → `--tk-duration-sm` (value: 0.2s → 0.35s)
- `--tk-duration-md` → kept (0.8s)
- `--tk-border-2xs` → `--tk-border-xs` (1px)
- `--tk-duration-xs` (line 77) → `--tk-duration-sm` (0.2s → 0.35s)
- `--tk-duration-md` (line 225) → kept (0.8s)

### `forms.css`
- `--tk-radius-full` → kept
- `--tk-duration-xs` → `--tk-duration-sm`
- `--tk-border-2xs` → `--tk-border-xs`
- `--tk-line-height-sm` → `--tk-line-height-md`

### `components.css`
- `--tk-duration-sm` → `--tk-duration-md` (0.5s → 0.8s — slower transition)
- `--tk-duration-md` (line 115) → kept
- `--tk-border-2xs` → `--tk-border-xs`
- `--tk-radius-4` → fix bug → `--tk-radius-sm` (4px)

### `layout.css`
- `--tk-border-xs` → `--tk-border-sm` (2px)

### `reset.css`
- `--tk-radius-full` → kept
- `--tk-line-height-md` → `--tk-line-height-lg` (1.5)
- `--tk-letter-spacing-lg` → kept
- `--tk-screen-2xl` → `--tk-screen-xl` (1440px)

---

## Notable Value Changes (visual impact)

| Consumer | Old | New | Change |
|----------|-----|-----|--------|
| `components.css` transitions | `--tk-duration-sm` 0.5s | `--tk-duration-md` 0.8s | +0.3s |
| `forms.css` transitions | `--tk-duration-xs` 0.2s | `--tk-duration-sm` 0.35s | +0.15s |
| `typography.css` transitions | `--tk-duration-xs` 0.2s | `--tk-duration-sm` 0.35s | +0.15s |
| `components.css` radius | `--tk-radius-4` (invalid) | `--tk-radius-sm` 4px | fixes bug |

---

## What Stays Unchanged

- Color system (`colors.css`) — factor/chroma/alpha naming
- Theme bg/fg (`theme.css`) — 1x–5x naming
- Font weights (100–900)
- Font stretch (named keywords)
- All fixed/locked value variables (border-style, display, position, overflow, cursor, alignment, etc.)
- 4px-based spacing scale (`--tk-size-4` through `--tk-size-100`)
- Percentage/viewport sizing (`--tk-size-5p` through `--tk-size-100vh`)
- Easing functions
- Animation presets (spin, ping, pulse, etc.)
- Text size scale (xs–9xl)
