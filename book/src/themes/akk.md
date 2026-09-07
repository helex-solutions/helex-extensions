# AKK

TEHIK's Andmekirjelduskeskkond — the Estonian health-data description environment.

| | Theme | Key | Mode |
|---|---|---|---|
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#0083BA" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#0083BA"></span><span title="#5D6071" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#5D6071"></span><span title="#DBDFE2" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#DBDFE2"></span></span> | **AKK** | `akk` | light |

## Install

Recommended — vendor the pack into the install and serve it from its own origin, so the shell is
not executing code fetched from another host before first paint:

```bash
APP_THEME_PACKS=akk          # fetch-theme-packs.sh downloads and verifies the sha256
APP_BOOTSTRAP_MODULES=/shell/themes/akk.js
APP_DEFAULT_THEME=akk
```

Development only — load it straight from this site, skipping the vendoring step:

```bash
APP_BOOTSTRAP_MODULES=https://helex-solutions.github.io/helex-extensions/packs/akk.js
```

Every theme here clears WCAG 2.1 AA for body text, for the label on a primary-filled button, and —
where the theme states a control border — the 3:1 floor for a control outline. That is asserted in
CI, not claimed here.
