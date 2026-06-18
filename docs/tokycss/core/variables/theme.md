# Theme Variable Tokens

Theme variable tokens are the primary way to build interfaces in Toky CSS.

Rather than applying raw theme color scales directly, you use semantic background and foreground tokens that automatically adapt to the active theme.

For example, instead of using:

```css
background: var(--tk-color-theme-5xlight);
```

Use:

```css
background: var(--tk-bg-5x);
```

Toky CSS handles the theme mapping automatically, allowing the same component styles to work across light mode, dark mode, and custom theme overrides without additional styling.

## How the Theme System Works

Toky CSS maps theme color scales to semantic roles.

### Light Mode

* Backgrounds use theme tints
* Foregrounds use theme shades

### Dark Mode

* Backgrounds use theme shades
* Foregrounds use theme tints

This inversion preserves visual hierarchy and contrast while keeping component styles unchanged across themes.

Toky CSS also uses the `color-scheme` property to integrate with browser-native UI, ensuring elements such as the following automatically match the active theme:

* Form controls
* Input fields
* Textareas
* Select menus
* Scrollbars
* Autofill UI
* Other browser-managed interface elements

## Theme Sources

Toky CSS can adapt to themes from multiple sources:

1. System preference (via CSS `light-dark()`)
2. Application theme switchers
3. Manual `data-theme` overrides

By default, Toky CSS follows the user's system preference.

When a theme switcher is used, the selected theme can be applied through the `data-theme` attribute and optionally persisted using local storage.

## Usage Priority

When building interfaces, follow this order:

1. Use `--tk-bg-*` for surfaces and layout backgrounds
2. Use `--tk-fg-*` for text and icons
3. Use semantic status tokens for feedback states
4. Use raw color scales for branding, marketing sections, and custom visual treatments

Most application interfaces should be built primarily with semantic theme tokens.

---

## Background Tokens

Background tokens define the visual hierarchy of surfaces.

### Scale Meaning

* `1x` = strongest emphasis
* `2x` = strong emphasis
* `3x` = moderate emphasis
* `4x` = subtle emphasis
* `5x` = lowest emphasis

### Recommended Usage

| Variable     | Recommended Usage                                     |
| ------------ | ----------------------------------------------------- |
| `--tk-bg-1x` | Active states, pressed states, high-emphasis surfaces |
| `--tk-bg-2x` | Inputs, hover states, subtle UI elements              |
| `--tk-bg-3x` | Nested surfaces, cards inside sections                |
| `--tk-bg-4x` | Sections, cards, low-contrast surfaces                |
| `--tk-bg-5x` | Page background, application shell, base layer        |

### Theme Mapping

| Variable     | Light Mode | Dark Mode |
| ------------ | ---------- | --------- |
| `--tk-bg-1x` | 1st tint   | 1st shade |
| `--tk-bg-2x` | 2nd tint   | 2nd shade |
| `--tk-bg-3x` | 3rd tint   | 3rd shade |
| `--tk-bg-4x` | 4th tint   | 4th shade |
| `--tk-bg-5x` | 5th tint   | 5th shade |

---

## Foreground Tokens

Foreground tokens control text, icons, borders, and other content.

### Scale Meaning

* `1x` = lowest contrast
* `2x` = subtle contrast
* `3x` = moderate contrast
* `4x` = high contrast
* `5x` = highest contrast

### Recommended Usage

| Variable     | Recommended Usage                        |
| ------------ | ---------------------------------------- |
| `--tk-fg-1x` | Decorative content, low-emphasis details |
| `--tk-fg-2x` | Muted text and icons                     |
| `--tk-fg-3x` | Secondary text                           |
| `--tk-fg-4x` | Primary text                             |
| `--tk-fg-5x` | Highest contrast text and icons          |

### Theme Mapping

| Variable     | Light Mode | Dark Mode |
| ------------ | ---------- | --------- |
| `--tk-fg-1x` | 1st shade  | 1st tint  |
| `--tk-fg-2x` | 2nd shade  | 2nd tint  |
| `--tk-fg-3x` | 3rd shade  | 3rd tint  |
| `--tk-fg-4x` | 4th shade  | 4th tint  |
| `--tk-fg-5x` | 5th shade  | 5th tint  |

---

## Status Background Tokens

Status background tokens are intended for alerts, notices, validation messages, badges, banners, and feedback surfaces.

| Variable          | Purpose                |
| ----------------- | ---------------------- |
| `--tk-bg-success` | Success surfaces       |
| `--tk-bg-warning` | Warning surfaces       |
| `--tk-bg-error`   | Error surfaces         |
| `--tk-bg-info`    | Informational surfaces |

---

## Status Foreground Tokens

Status foreground tokens are intended for text, icons, and indicators displayed on status surfaces.

| Variable          | Purpose                      |
| ----------------- | ---------------------------- |
| `--tk-fg-success` | Success text and icons       |
| `--tk-fg-warning` | Warning text and icons       |
| `--tk-fg-error`   | Error text and icons         |
| `--tk-fg-info`    | Informational text and icons |

### Example

```css
.alert {
  background-color: var(--tk-bg-warning);
  color: var(--tk-fg-warning);
}
```

---

## Focus Tokens

Focus indicators intentionally use brand colors rather than theme colors.

This helps maintain visibility and consistency across themes.

| Variable              | Purpose                                      |
| --------------------- | -------------------------------------------- |
| `--tk-focus-ring`     | Primary focus indicator |

### Example

```css
.button:focus-visible {
  outline: 2px solid var(--tk-focus-ring);
}
```

---

## Theme Overrides

By default, Toky CSS follows the user's system theme.

You can override the active theme by applying the `data-theme` attribute to the document root or any themed container.

### Follow System Preference

```html
<html data-theme="system">
```

### Force Light Mode

```html
<html data-theme="light">
```

### Force Dark Mode

```html
<html data-theme="dark">
```

### Theme a Specific Section

```html
<section data-theme="dark">
  ...
</section>
```

### Supported Values

* `system`
* `light`
* `dark`

This makes it possible to create themed sections, sidebars, modals, widgets, marketing blocks, and other isolated interface areas without affecting the rest of the page.
