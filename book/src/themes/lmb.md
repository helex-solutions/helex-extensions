# LMB

Lietuvos medicinos biblioteka — the Lithuanian Health Sciences Library.

| | Theme | Key | Mode |
|---|---|---|---|
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#0079BF" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#0079BF"></span><span title="#36373D" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#36373D"></span><span title="#EEEEEE" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#EEEEEE"></span></span> | **LMB** | `lmb` | light |

## Install

Recommended — vendor the pack into the install and serve it from its own origin, so the shell is
not executing code fetched from another host before first paint:

```bash
APP_THEME_PACKS=lmb          # fetch-theme-packs.sh downloads and verifies the sha256
APP_BOOTSTRAP_MODULES=/shell/themes/lmb.js
APP_DEFAULT_THEME=lmb
```

Development only — load it straight from this site, skipping the vendoring step:

```bash
APP_BOOTSTRAP_MODULES=https://helex-solutions.github.io/helex-extensions/packs/lmb.js
```

Every theme here clears WCAG 2.1 AA for body text, for the label on a primary-filled button, and —
where the theme states a control border — the 3:1 floor for a control outline. That is asserted in
CI, not claimed here.
