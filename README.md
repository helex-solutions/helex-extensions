# Helex extensions

Themes — and, later, menu contributions — that a [Helex EMR](https://github.com/helex-solutions/emr-repo)
installation can load without a rebuild.

**Browse the catalogue: <https://helex-solutions.github.io/helex-extensions>**

## This repository is generated

Everything here except this README and `.github/` is produced by
`scripts/build-theme-packs.mjs` in `helex-solutions/emr-repo` and mirrored by its
`Publish Theme Catalogue` workflow. **Do not edit `packs/`, `manifest.json` or `book/src/` here** —
the next publish overwrites it, and a hand-edited pack whose bytes no longer match the `sha256` in
`manifest.json` makes every install's integrity check fail against an honest catalogue.

To change a theme, change it in `emr-repo`:

| What | Where in emr-repo |
|---|---|
| `helex`, `tedi`, `matrix` | `modules/core/frontend/libs/ui/src/lib/themes/themes.ts` |
| `evergreen`, `slate`, `wireframe`, `taltech` | `scripts/theme-packs/catalogueThemes.mjs` |
| The generator, store pages, manifest shape | `scripts/build-theme-packs.mjs` |

## Layout

```
packs/*.js       the extension packs an install loads
manifest.json    id, url, sha256 and theme swatches for every pack
book/            mdBook source for the catalogue site
```

## Using a pack

Recommended — vendor it into the install and serve it same-origin, so the shell is not executing
code fetched from another host before first paint:

```bash
APP_THEME_PACKS=taltech          # deployment/server/fetch-theme-packs.sh verifies the sha256
APP_BOOTSTRAP_MODULES=/shell/themes/taltech.js
APP_DEFAULT_THEME=taltech
```

Development only — load straight from this site:

```bash
APP_BOOTSTRAP_MODULES=https://helex-solutions.github.io/helex-extensions/packs/taltech.js
```

A dynamic `import()` cannot carry a Subresource Integrity hash, which is why `manifest.json`
publishes a digest per pack and production installs verify it at deploy time rather than trusting
this origin at boot.
