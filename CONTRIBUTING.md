# Contributing to DialKit

Thanks for contributing.

## Development setup

1. Fork and clone the repo.
2. Install dependencies with `npm i`.
3. Run `npm run typecheck` and `npm run build` before opening a PR.

## Toolbar browser checks

After `npm run build`, run `node scripts/build-toolbar-fixtures.mjs` and serve `.toolbar-fixtures` on port 3011 (for example, `python3 -m http.server 3011 --directory .toolbar-fixtures`). The fixtures cover panels and timelines in all five frameworks; append `?theme=dark` to inspect dark mode.

With Playwright and Chrome installed, run `node scripts/test-toolbar-browser.mjs` to check version creation, selection, deletion, numbering, and keyboard focus. `DIALKIT_PLAYWRIGHT` can point to an existing Playwright installation, and `DIALKIT_FIXTURE_URL` overrides the server URL.

## Project notes

- `src/styles/theme.css` is copied to `dist/styles.css` during build via `tsup` `onSuccess`.
- `example/photostack` imports `dialkit/styles.css`, which resolves to `dist/styles.css`.
- `ButtonGroup` actions should remain vertically stacked.

## Pull request guidelines

- Keep PRs single-responsibility and small.
- Include a short summary of what changed and why.
- Add validation notes (for example: `npm run typecheck`, `npm run build`).
- Update `README.md` when behavior or API docs change.
