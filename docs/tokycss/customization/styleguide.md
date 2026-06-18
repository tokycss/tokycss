# Styleguide

The styleguide is the central customization file in Toky CSS.

While the filename itself is not required, the structure and variables inside it are. Nearly every customization feature in the framework depends on values defined here.

You can think of the styleguide as the project's design foundation. It defines the visual decisions that the rest of the framework builds upon.

## Creating a Styleguide

Create a CSS file and add a `styleguide` layer.

```css
@layer styleguide {
  :root {
    /* Your customization */
  }
}
```

The file can be named anything:

```text
styleguide.css
brand.css
theme.css
project.css
```

However, `styleguide.css` is recommended because it clearly communicates the file's purpose to anyone working on the project.

## Why Use a Separate Styleguide?

As projects grow, design decisions tend to spread across many files.

A color gets overridden in one component. A font changes somewhere else. A layout rule appears in a utility class months later.

Keeping core design decisions in a dedicated styleguide creates a single source of truth for the project.

When someone asks:

> What colors does this project use?

or

> Where do I change the typography?

There is one obvious place to look.

## What Lives in the Styleguide?

The styleguide contains four areas of customization:

| Section      | Purpose                                            |
| ------------ | -------------------------------------------------- |
| Brand Colors | Defines the project's visual identity              |
| Theme Color  | Shapes neutral surfaces and themes                 |
| Typography   | Defines font families and text roles               |
| Layout       | Controls content width, gutters, and fluid scaling |

Each area is covered in detail throughout the next sections.

## Complete Styleguide

This is the default styleguide shipped with Toky CSS.

You can copy it directly into a project and customize it as needed.

```css
@layer styleguide {
  :root {
    /* BRAND COLORS */
    --tk-color-primary: oklch(0.52 0.20 270);
    --tk-color-secondary: oklch(0.62 0.14 195);
    --tk-color-accent: oklch(0.72 0.17 75);

    /* Theme hue */
    --tk-color-theme: oklch(0.95 0.008 265);

    /* TYPOGRAPHY */
    --tk-font-sans: "Inter", "SF Pro Display", -apple-system,
      BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;

    --tk-font-serif: "Georgia", "Times New Roman", serif;

    --tk-font-mono: "JetBrains Mono", "Fira Code",
      "SF Mono", Consolas, monospace;

    --tk-font-display: var(--tk-font-sans);
    --tk-font-heading: var(--tk-font-sans);
    --tk-font-body: var(--tk-font-sans);
    --tk-font-num: var(--tk-font-mono);

    /* LAYOUT */
    --tk-page-gutter: var(--tk-size-20);
    --tk-content-width: 80ch;
    --tk-content-fill-width: 90ch;

    /* FLUID TYPOGRAPHY */
    --tk-fluid-scale-start: 480;
    --tk-fluid-scale-end: 1440;
  }
}
```

Next, we'll look at Branding and learn how a small set of color decisions expands into the color system used throughout a project.
