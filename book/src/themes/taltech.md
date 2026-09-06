# TalTech

Tallinn University of Technology, from the published TalTech design system.

| | Theme | Key | Mode |
|---|---|---|---|
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#342b60" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#342b60"></span><span title="#e4067e" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#e4067e"></span><span title="#f6f6f8" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#f6f6f8"></span></span> | **TalTech** | `taltech` | light |

## Install

Recommended — vendor the pack into the install and serve it from its own origin, so the shell is
not executing code fetched from another host before first paint:

```bash
APP_THEME_PACKS=taltech          # fetch-theme-packs.sh downloads and verifies the sha256
APP_BOOTSTRAP_MODULES=/shell/themes/taltech.js
APP_DEFAULT_THEME=taltech
```

Development only — load it straight from this site, skipping the vendoring step:

```bash
APP_BOOTSTRAP_MODULES=https://helex-solutions.github.io/helex-extensions/packs/taltech.js
```

Every theme here clears WCAG 2.1 AA for body text, for the label on a primary-filled button, and —
where the theme states a control border — the 3:1 floor for a control outline. That is asserted in
CI, not claimed here.
