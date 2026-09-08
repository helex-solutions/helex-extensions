# Tervisekassa

The Estonian Health Insurance Fund, from their published stiiliraamat 2026.

| | Theme | Key | Mode |
|---|---|---|---|
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#105B9E" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#105B9E"></span><span title="#A03170" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#A03170"></span><span title="#F5F8FB" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#F5F8FB"></span></span> | **Tervisekassa** | `tervisekassa` | light |

## Install

Recommended — vendor the pack into the install and serve it from its own origin, so the shell is
not executing code fetched from another host before first paint:

```bash
APP_THEME_PACKS=tervisekassa          # fetch-theme-packs.sh downloads and verifies the sha256
APP_BOOTSTRAP_MODULES=/shell/themes/tervisekassa.js
APP_DEFAULT_THEME=tervisekassa
```

Development only — load it straight from this site, skipping the vendoring step:

```bash
APP_BOOTSTRAP_MODULES=https://helex-solutions.github.io/helex-extensions/packs/tervisekassa.js
```

Every theme here clears WCAG 2.1 AA for body text, for the label on a primary-filled button, and —
where the theme states a control border — the 3:1 floor for a control outline. That is asserted in
CI, not claimed here.
