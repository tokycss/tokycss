# Effects

## Shadow System

Layered shadows built from the theme shadow colour, so they follow light/dark mode automatically.

| Variable | Elevation |
|---|---|
| `--tk-shadow-xs` | Hairline lift |
| `--tk-shadow-sm` | Subtle card |
| `--tk-shadow-md` | Raised surface |
| `--tk-shadow-lg` | Floating panel |
| `--tk-shadow-xl` | Modal / overlay |

```css
.card {
  box-shadow: var(--tk-shadow-sm);
}

.modal {
  box-shadow: var(--tk-shadow-xl);
}
```

## Filters

Filters are one function call — `blur(4px)` is shorter and clearer than a token for it. Use them directly:

```css
.modal-backdrop {
  backdrop-filter: blur(4px);
}

.disabled-image {
  filter: grayscale(100%);
}
```

## Opacity

Opacity is a plain number. Write it directly:

```css
.dimmed {
  opacity: 0.5;
}

.hidden {
  opacity: 0;
}
```
