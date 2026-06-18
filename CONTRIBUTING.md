# Contributing

Toky CSS is in early development (v0.1.0). The API is still stabilizing.

## Currently

- **Bug reports and feature suggestions** are welcome via GitHub Issues
- **Pull requests** are not yet the primary contribution path while the foundation solidifies, but feel free to open one for discussion

## How to Contribute

1. Check existing [issues](https://github.com/tokycss/tokycss/issues) before opening a new one
2. Open a GitHub Issue for bugs, suggestions, or questions
3. For design discussions, open an issue with the question first — this helps us discuss before code is written

## Development Setup

```bash
git clone https://github.com/tokycss/tokycss.git
cd tokycss
npm install
npm run dev     # starts dev server with live reload
npm run build   # builds dist files
```

## Code Style

- CSS follows the existing conventions in `src/` — comments, formatting, variable naming
- Run `npm run lint` and `npm run stylelint` before committing
- The project uses Prettier and ESLint — formatting is enforced

## Commit Messages

Use conventional commits:

- `feat:` — new feature
- `fix:` — bug fix
- `refactor:` — code change with no behavior change
- `docs:` — documentation
- `chore:` — build, tooling, dependencies

## Questions?

Open a [GitHub Discussion](https://github.com/tokycss/tokycss/discussions) or issue.
