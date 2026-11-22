# Border Variables

## Border Radius

Controls the roundness of element corners. This is the only border decision Toky tokenises — it is a design-language choice, not a CSS value.

| Variable | Value | Visual |
|---|---|---|
| `--tk-radius-0` | 0 | Sharp corners |
| `--tk-radius-xs` | 2px | Barely visible |
| `--tk-radius-sm` | 4px | Soft |
| `--tk-radius-md` | 8px | Standard |
| `--tk-radius-lg` | 12px | Prominent |
| `--tk-radius-xl` | 16px | Very rounded |
| `--tk-radius-full` | 9999px | Fully round (circles/pills) |

```css
.button {
  border-radius: var(--tk-radius-sm);
}

.avatar {
  border-radius: var(--tk-radius-full);
}
```

## Border Width

Use native CSS. Border widths are short, self-describing units, so a token only adds typing:

```css
.card {
  border: 1px solid var(--tk-fg-theme-2x);
}
```

## Border Style

Use the native keyword directly — `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset`.

```css
.rule {
  border-bottom: 1px dashed var(--tk-fg-theme-2x);
}
```

## Outline

Outline width and style are native CSS too:

```css
:focus-visible {
  outline: 2px solid var(--tk-focus-ring);
  outline-offset: 2px;
}
```
