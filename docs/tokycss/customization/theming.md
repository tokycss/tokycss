# Themes

Themes control how your interface adapts to different viewing preferences.

By default, Toky CSS follows the user's preferred color scheme. If someone prefers dark mode, the framework automatically switches to dark mode. If they prefer light mode, the framework uses light mode.

No JavaScript is required.

---

## Theme Sources

Toky CSS can receive theme information from several places.

| Source          | Description                                              |
| --------------- | -------------------------------------------------------- |
| System          | Uses the user's operating system preference              |
| Browser         | Uses the browser's preferred color scheme when available |
| Theme Switcher  | Controlled by your application                           |
| Manual Override | Applied through `data-theme`                             |

Most projects simply follow the user's preference.

As more applications adopt theme switchers, users increasingly expect interfaces to remember their chosen theme across devices and sessions.

Toky CSS is designed to support both approaches.

---

## Following System Preferences

By default, Toky CSS follows the user's preferred color scheme through the CSS `light-dark()` function.

If a user changes their operating system theme, supported browsers automatically update the interface.

No additional configuration is required.

---

## Theme Switchers

Many applications provide a light mode and dark mode toggle.

Toky CSS works well with this pattern.

A theme switcher typically updates a `data-theme` attribute and optionally stores the user's choice in local storage.

The framework then applies the appropriate theme automatically.

How you implement the switcher is entirely up to your application.

---

## Manual Theme Overrides

You can force a specific theme by applying a `data-theme` attribute.

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

---

## Theming Individual Sections

Theme overrides are not limited to the root element.

Any container can become its own themed region.

```html
<section data-theme="dark">
  ...
</section>
```

```html
<aside data-theme="light">
  ...
</aside>
```

```html
<div data-theme="dark">
  ...
</div>
```

This makes it possible to create:

* Dark sidebars inside light applications
* Light marketing sections inside dark pages
* Embedded widgets
* Documentation examples
* Dashboards
* Modals

without affecting the rest of the interface.

---

## Browser Integration

Toky CSS uses the `color-scheme` property to help browser-managed UI match the active theme.

This includes elements such as:

* Form controls
* Input fields
* Textareas
* Select menus
* Scrollbars
* Autofill interfaces

As browsers continue exposing more native UI controls to CSS, this integration becomes increasingly valuable for maintaining visual consistency.

---

## Looking Ahead

Today, Toky CSS ships with:

* Light mode
* Dark mode
* System mode

The theme system is designed so additional theme variations can be added in the future without requiring changes to component styles.

That flexibility is one reason Toky CSS encourages building interfaces with theme-aware tokens rather than hard-coded colors.

---

## Next Step

Now that you understand how themes are selected and applied, continue to the Core Variables documentation to learn how Toky CSS maps colors into usable interface tokens.
