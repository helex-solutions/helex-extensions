# Classic Helex palettes

Evergreen, Slate and Wireframe — shipped with EMR until the catalogue existed.

| | Theme | Key | Mode |
|---|---|---|---|
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#2D7A4F" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#2D7A4F"></span><span title="#3A7CA5" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#3A7CA5"></span><span title="#F4F8F5" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#F4F8F5"></span></span> | **Evergreen** | `evergreen` | light |
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#455A75" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#455A75"></span><span title="#6B7A8F" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#6B7A8F"></span><span title="#F5F6F8" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#F5F6F8"></span></span> | **Slate** | `slate` | light |
| <span style="display:inline-flex;gap:2px;vertical-align:middle"><span title="#595959" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#595959"></span><span title="#8C8C8C" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#8C8C8C"></span><span title="#FAFAFA" style="display:inline-block;width:28px;height:28px;border:1px solid #0002;background:#FAFAFA"></span></span> | **Wireframe** | `wireframe` | light |

## Install

Recommended — vendor the pack into the install and serve it from its own origin, so the shell is
not executing code fetched from another host before first paint:

```bash
APP_THEME_PACKS=legacy          # fetch-theme-packs.sh downloads and verifies the sha256
APP_BOOTSTRAP_MODULES=/shell/themes/legacy.js
APP_DEFAULT_THEME=evergreen
```

Development only — load it straight from this site, skipping the vendoring step:

```bash
APP_BOOTSTRAP_MODULES=https://helex-solutions.github.io/helex-extensions/packs/legacy.js
```

Every theme here clears WCAG 2.1 AA for body text, for the label on a primary-filled button, and —
where the theme states a control border — the 3:1 floor for a control outline. That is asserted in
CI, not claimed here.
