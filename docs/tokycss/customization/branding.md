# Branding

Branding is where your project starts to look like your project.

Inside `styleguide.css`, Toky CSS exposes four color variables that define the visual identity of your interface:

```css
/* BRAND COLORS */
--tk-color-primary: oklch(0.52 0.20 270);
--tk-color-secondary: oklch(0.62 0.14 195);
--tk-color-accent: oklch(0.72 0.17 75);

/* THEME COLOR */
--tk-color-theme: oklch(0.95 0.008 265);
```

For most projects, these are the only color values you need to customize.

---

## Brand Colors

Brand colors are the colors people notice.

They communicate identity, guide attention, and help users recognize interactive elements throughout your interface.

| Variable               | Purpose                 |
| ---------------------- | ----------------------- |
| `--tk-color-primary`   | Main brand color        |
| `--tk-color-secondary` | Supporting brand color  |
| `--tk-color-accent`    | Highlights and emphasis |

A common pattern is:

* Primary for buttons, links, and actions
* Secondary for supporting elements
* Accent for highlights, badges, and callouts

```css
--tk-color-primary: oklch(0.52 0.20 270);
--tk-color-secondary: oklch(0.62 0.14 195);
--tk-color-accent: oklch(0.72 0.17 75);
```

---

## The 60 / 30 / 10 Rule

If you are unsure how to balance your colors, the classic 60 / 30 / 10 rule is a useful starting point.

| Percentage | Role                             |
| ---------- | -------------------------------- |
| 60%        | Theme color and neutral surfaces |
| 30%        | Primary brand color              |
| 10%        | Either secondary or accent color                     |

This is not a strict rule.

It simply helps prevent every element from competing for attention at the same time.

In most interfaces, neutral surfaces do most of the visual work while brand colors draw attention where it matters.

---

## Theme Color

The theme color controls the overall tone of the interface.

```css
--tk-color-theme: oklch(0.95 0.008 265);
```

Unlike brand colors, the theme color usually stays subtle.

It influences surfaces such as:

* Page backgrounds
* Sections
* Cards
* Panels
* Containers
* Borders

Many modern products slightly tint their neutral colors toward their brand rather than using pure gray.

A small amount of color often feels more intentional without becoming distracting.

```css
/* Slight blue tint */
--tk-color-theme: oklch(0.95 0.008 265);
```

```css
/* Pure neutral gray */
--tk-color-theme: oklch(0.95 0 0);
```

As a general rule, keep chroma low.

The theme color should support the interface, not compete with it.

---

## Any CSS Color Format Works

You can use any valid CSS color format.

```css
--tk-color-primary: #1a53ff;
```

```css
--tk-color-primary: rgb(26 83 255);
```

```css
--tk-color-primary: hsl(223 100% 55%);
```

```css
--tk-color-primary: oklch(0.52 0.20 270);
```

OKLCH is recommended because it provides predictable control over lightness and saturation, but it is not required.

---

## What Happens After You Choose Your Colors?

Toky CSS automatically generates additional color values from every brand and theme color.

You define one color:

```css
--tk-color-primary: #1a53ff;
```

Toky CSS generates:

* 5 lighter tints
* 5 darker shades
* 10 alpha variants

The same happens for:

* Primary
* Secondary
* Accent
* Theme

This means a handful of color decisions become a complete color system automatically.

The generated scales are covered in detail later in the Colors documentation.

---

## Choosing Good Colors

Picking colors is often harder than writing code.

If you need a starting point, visual palette generators can help you explore combinations quickly.

> **Tip:** Huemint is a great starting point for generating website color palettes:
>
> https://huemint.com/website-2/#palette=feffff-1a53ff-00ffee-fab700

The goal is not to find perfect colors immediately.

Choose a direction, build a few screens, then adjust based on how the interface feels in practice.

---

## Next Step

Now that your brand colors and theme color are defined, the next step is understanding how those colors behave across light mode and dark mode.

Continue to **Themes**.
