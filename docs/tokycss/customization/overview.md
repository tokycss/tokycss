# Customization Overview

Every project has a style guide, whether it is written down or not.

Someone chooses the colors. Someone picks the fonts. Someone decides how wide content should be, how headings should look, and how the interface should feel.

Toky CSS brings those decisions together in a single place: `styleguide.css`.

Rather than spreading design decisions across components, utilities, overrides, and custom CSS files, you define the foundation once and let the framework build from it.

This approach keeps customization predictable as a project grows. A color change affects the entire color system. A typography change updates every heading and paragraph. A layout adjustment flows through the whole interface.

## The Styleguide as Your Design Foundation

The styleguide is the anchor of a Toky CSS project.

It defines:

| Area       | Purpose                                     |
| ---------- | ------------------------------------------- |
| Branding   | Project colors and visual identity          |
| Typography | Fonts and text roles                        |
| Layout     | Content width and page spacing              |
| Themes     | The visual tone of surfaces and backgrounds |

Without a styleguide, Toky CSS still works. However, most of the framework's customization capabilities remain unused.

The framework was designed around the assumption that each project has its own identity. The styleguide is where that identity lives.

## One File, One Workflow

Modern frontend projects often involve multiple tools, design systems, frameworks, and contributors.

Toky CSS keeps customization intentionally simple.

Instead of maintaining configuration across multiple files, your project's core design decisions live in one place:

```css
@layer styleguide {
  :root {
    /* Project customization */
  }
}
```

This makes it easier to understand how a project is branded, easier to onboard new team members, and easier to make changes months later when the original decisions are no longer fresh in memory.

## What You'll Customize

The next sections walk through each part of the styleguide:

* Branding
* Typography
* Layout
* Themes

You'll then finish with a complete styleguide file that can be copied directly into a project and customized as needed.
