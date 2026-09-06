# Helex extensions

Themes — and, later, menu contributions — that a Helex EMR installation can load without a rebuild.

EMR itself ships three themes: **Helex**, **TEDI** and **Matrix**. Everything else lives here. An
install names the packs it wants and gets exactly those in its theme picker.

| Pack | Themes | |
|---|---|---|
| [Helex platform themes](themes/platform.md) | `helex`, `tedi`, `matrix` | Helex, TEDI and Matrix — the three themes EMR ships with. Included for reference. |
| [Classic Helex palettes](themes/legacy.md) | `evergreen`, `slate`, `wireframe` | Evergreen, Slate and Wireframe — shipped with EMR until the catalogue existed. |
| [TalTech](themes/taltech.md) | `taltech` | Tallinn University of Technology, from the published TalTech design system. |

## How a pack works

A pack is one ES module that the shell imports **before the application starts** — early enough
that a theme registered by it is indistinguishable from one compiled in. It imports nothing and
reads the platform's own React, antd and registries from `window.__helexPlatform`.

```js
const ui = window.__helexPlatform.ui;
ui.registerTheme('mytheme', { name: 'My theme', colorPrimary: '#123456', /* … */ });
```

Two rules, both load-bearing:

1. **Register a theme synchronously, at module top level.** `@helex/state` resolves the active
   theme when it is evaluated. A theme registered after `await platform.state()` is dropped
   without an error.
2. **Never `import` `@helex/ui`.** A second copy of React breaks hooks, and a second registry
   means the shell never sees the registration.

Anything that genuinely needs `@helex/state` goes in an exported `boot()`, which the shell
awaits after the module has evaluated.

## Integrity

`manifest.json` carries a `sha256` for every pack. A dynamic `import()` cannot carry a
Subresource Integrity hash, so production installs download packs at deploy time, verify that
digest, and serve them from their own origin. Pointing `APP_BOOTSTRAP_MODULES` straight at this
site is supported for development, where the trade is worth it.
