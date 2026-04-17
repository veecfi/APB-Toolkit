<div align="center">


# APB Reloaded Toolkit

**The all-in-one config manager, launcher, and GFAC tool for APB Reloaded.**

[![Version](https://img.shields.io/badge/version-2.1.0-blue?style=flat-square)](https://github.com/veecfi/APB-Toolkit/releases)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey?style=flat-square&logo=windows)](https://github.com/veecfi/APB-Toolkit)
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1-blue?style=flat-square&logo=powershell)](https://github.com/veecfi/APB-Toolkit)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

[**Download Latest**](https://github.com/veecfi/APB-Toolkit/releases/latest) · [**Report Bug**](https://github.com/veecfi/APB-Toolkit/issues) · [**Request Feature**](https://github.com/veecfi/APB-Toolkit/issues)

</div>

---

## ✨ What is this?

APB Reloaded Toolkit is a borderless WinForms app built in PowerShell that replaces the tedious process of manually copying config files into your APB install. Select cards, set your apply order, load presets, manage GFAC, and launch the game — all from one clean interface with full **dark and light mode** support.

No Python. No dependencies. No install. Just drop it in your configs folder and run.

---

## 🖼️ Interface

| Dark Mode | Light Mode |
|---|---|
| Borderless dark UI with card grid | Full light theme with proper contrast |

> The interface opens on **Preset Configs** by default. Navigate using the sidebar.

---

## 🗂️ Features

### ⚙️ Config Options

<details>
<summary><b>Preset Configs</b> — Save and load full config setups</summary>

- Three built-in presets: **Default**, **Performance**, **High Quality**
- Save your current selection as a named preset
- Load, Edit, Rename and Delete user presets
- Shows how many options each preset has saved
- Loading fully restores all selections — including sub-option choices
- Built-in presets anchored at the top; yours scroll below

</details>

<details>
<summary><b>Advanced</b> — Card picker for all your config folders</summary>

- Each folder in the toolkit directory becomes a **card**
- Click to select (turns blue), click again to deselect
- Cards with sub-folders open a **drill-down chooser**
- **Filter pills** — `imported` shows folders you added, `default` shows folders that shipped with the toolkit
- **Text search** — filter cards by name in real time
- **Card count** shown top right
- Overwrite, Backup, -nosteam and -nosplash checkboxes on one row
- Conflict detection warns when two selected configs overwrite the same file
- Auto-backup of `APBGame\Config` before applying (when Backup is enabled)

</details>

<details>
<summary><b>Import Config</b> — Bring in external config folders</summary>

- Browse for any folder — see path, file count, and size before confirming
- Copied into the toolkit directory automatically
- Tracked in `imported_folders.json` so the `imported` filter pill works correctly

</details>

<details>
<summary><b>Config Order</b> — Control exact apply sequence</summary>

- Drag rows up/down to reorder — smooth drag with no flicker
- `^` move up · `vv` send to bottom · `X` remove and deselect
- Overwrite, Backup, -nosteam and -nosplash checkboxes mirrored here
- Activity log shows per-file output: **OK / SKIP / FAIL**
- Apply order persists across sessions in `settings.json`

</details>

---

### 🔧 Utilities

| Section | Tools |
|---|---|
| **APB Options** | Launch/Update · Repair Game · Uninstall · Reinstall |
| **GFAC Options** | Run Updater · Uninstall (+ TPI folder) · Reinstall |
| **Other** | Open Game Folder · Open Steam · Target Flags shortcuts |

> Launch/Update and Repair use **APBLauncher.exe** directly — no Steam URI roundtrip.
> GFAC Uninstall and Reinstall also remove the `TPI` folder alongside `C:\Program Files\GFAC`.

---

### 🚀 Sidebar

| Button | Behaviour |
|---|---|
| **Update APB** | Launches APBLauncher.exe — turns Play yellow until reapplied |
| **Play APB** | Launches via shortcut and **closes the toolkit** |

Play turns **yellow** after updating (prompts confirmation before launching) and **red** when flagged files are selected.

---

### 🛡️ Safety

Files that trigger GFAC shadowbans are flagged with an **amber warning triangle** on the card. Apply Selected warns before copying any flagged content.

**Safe whitelist:** `.ini` `.ger` `.int` `.apb` `.txt` `.md` · `vivoxvoiceservice.exe`

---

### 🎨 Settings

- **Updates** — Version card, Check for Updates, auto-download and relaunch via temp-file swap
- **Preferences** — Dark/Light toggle · APB path · Backup/Restore · Descriptions Export/Import/Clear · Reset Selections · Open Folder

---

## 📦 Installation

1. Download the latest release from the [**Releases**](https://github.com/veecfi/APB-Toolkit/releases) page
2. Extract to a dedicated folder — e.g. `C:\APB Toolkit\`
3. Run `APBToolkit.exe` — no install, no setup, just launch
4. Set your APB directory in **Advanced**, then **Settings → Preferences → Save Path**

> **No admin rights required. No installation. No registry changes.**
> The download comes as a ready-to-run compiled `.exe` — no PowerShell or build steps needed.

---

## 🗃️ Folder Structure

```
APB Toolkit\
  APBToolkit.exe                ← run this to launch the toolkit
  descriptions.json             ← card descriptions
  presets.json                  ← saved presets
  settings.json                 ← app settings
  imported_folders.json         ← tracks imported folders
  │
  ├── Icons\
  │     APBToolkit.ico          ← window + taskbar icon
  │
  ├── Images\
  │     launch.png  repair.png  gfac.png  ...
  │
  ├── Backups\
  │     AutoBackup_20250101_120000.zip
  │
  ├── Default Preset\
  │     APBGame\Config\DefaultGame.ini
  │
  ├── My Custom Config\
  │     APBGame\Config\DefaultEngine.ini
  │     Engine\Config\BaseEngine.ini
  │
  └── Multi Option Folder\
        Option A\APBGame\Config\...
        Option B\APBGame\Config\...
```

> **Reserved folders** (never shown as cards): `APBGame` `Engine` `Icons` `Images` `Backups`

---

## ➕ Adding Your Own Configs

1. Create a folder next to the exe — e.g. `My HUD Fix\`
2. Replicate the APB directory structure inside it:
   ```
   My HUD Fix\
     APBGame\
       Config\
         DefaultUI.ini
   ```
3. Click **Refresh** in Advanced — your card appears instantly
4. Select it and click **Apply Selected**

For multiple variants (colour choices, quality levels etc.), create **subfolders** inside your option folder. The toolkit shows a **Choose** button and opens a drill-down chooser.

---


## 🚩 Launch Flags

| Flag | Effect |
|---|---|
| `-language=1031` | Loads custom localisation files |
| `-nomovies` | Skips intro movies |
| `-nosplash` | Skips splash screen |
| `-nosteam` | Disables Steam integration |

Toggling `-nosteam` or `-nosplash` **immediately updates your desktop shortcut** — no need to click Play.

---

## 🖼️ Tool Card Images

Drop PNGs into `Images\` to customise Utilities cards:

| File | Card |
|---|---|
| `launch.png` | Launch / Update |
| `repair.png` | Repair Game |
| `uninstall.png` | Uninstall APB |
| `reinstall.png` | Reinstall APB |
| `gfac.png` | Run GFAC Updater |
| `gfac_uninstall.png` | Uninstall GFAC |
| `gfac_reinstall.png` | Reinstall GFAC |
| `folder.png` | Open Game Folder |
| `steam.png` | Open Steam |
| `flags.png` | Default Target Flags |
| `flags_adv.png` | Advanced Target Flags |

---

## 📋 Changelog

> Full changelog available in **Settings → Updates** inside the toolkit.

### v2.1.0 — Current
- Full dark ↔ light mode with complete theme coverage across all panels and buttons
- `imported` / `default` filter pills in Advanced (mutually exclusive)
- Imported folders tracked persistently in `imported_folders.json`
- Checkboxes (Overwrite, Backup, -nosteam, -nosplash) added to Config Order tab
- Config Order activity log shows per-file copy output (OK / SKIP / FAIL)
- Config Order drag rewritten — no flicker, smooth scroll follows dragged row
- Preset Load fully restores all selections including sub-option choices
- Update downloads to `%TEMP%`, swaps exe via bat file after process exits
- Launch/Update, Repair and Update APB use `APBLauncher.exe` directly
- GFAC Uninstall/Reinstall also removes the `TPI` folder
- Play APB closes the toolkit after launching
- Window buttons order fixed: Min / Max / Close
- Rounded button corners fixed — fully transparent, no background rectangle
- `Icons\` folder excluded from card list; reserved folders expanded
- Build script included for compiling with custom icon

### v1.5.x
- Config Order tab with drag-to-reorder
- Preset Configs redesign with built-in and user sections
- Import Config redesign with file info preview
- Auto-backup before applying
- Conflict detection between selected configs
- Update auto-download and relaunch
- Filter row in Advanced with card count
- -nosteam and -nosplash checkboxes with live shortcut sync

---

## ⚠️ Disclaimer

Use of modified game files is at your own risk. This tool only copies files you explicitly select. Always review what you're applying — some configs disable kiosks or streaming in ways that affect gameplay. The GFAC safe file whitelist is maintained conservatively; when in doubt, don't apply flagged files.

---

## 📄 License

MIT — see [`LICENSE`](LICENSE) for details.

---

<div align="center">

Made for the APB community · [veecfi](https://github.com/veecfi)

</div>
