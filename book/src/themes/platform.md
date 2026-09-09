# Helex platform themes

Helex, TEDI and Matrix — the three themes EMR ships with. Included for reference.

| | Theme | Key | Mode |
|---|---|---|---|
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#1B6AB3" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#1B6AB3"></span><span title="#2E7D6F" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#2E7D6F"></span><span title="#F5F7FA" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#F5F7FA"></span></span> | **Helex** | `helex` | light |
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#005AA3" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#005AA3"></span><span title="#FF8000" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#FF8000"></span><span title="#F9F9F9" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#F9F9F9"></span></span> | **TEDI** | `tedi` | light |
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#00FF41" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#00FF41"></span><span title="#3DDC84" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#3DDC84"></span><span title="#060E06" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#060E06"></span></span> | **Matrix** | `matrix` | dark |

## Install

Recommended — vendor the pack into the install and serve it from its own origin, so the shell is
not executing code fetched from another host before first paint:

```bash
APP_THEME_PACKS=platform          # fetch-theme-packs.sh downloads and verifies the sha256
APP_BOOTSTRAP_MODULES=/shell/themes/platform.js
APP_DEFAULT_THEME=helex
```

Development only — load it straight from this site, skipping the vendoring step:

```bash
APP_BOOTSTRAP_MODULES=https://helex-solutions.github.io/helex-extensions/packs/platform.js
```

Every theme here clears WCAG 2.1 AA for body text, for the label on a primary-filled button, and —
where the theme states a control border — the 3:1 floor for a control outline. That is asserted in
CI, not claimed here.
