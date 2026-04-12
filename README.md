# APB Reloaded Toolkit

> A clean, all-in-one config management and launcher tool for APB Reloaded — built with PowerShell WinForms.

---

## Overview

APB Reloaded Toolkit lets you manage, organise, and apply custom config files to APB Reloaded without manually copying folders or digging through your install directory. Select option cards, set your apply order, load presets, manage GFAC, and launch the game — all from one borderless dark-mode interface.

---

## Features

### Config Options
- **Preset Configs** — Three built-in presets (Default, Performance, High Quality) always available. Save, load, edit, rename and delete your own custom presets. Built-in presets are anchored at the top; your saved presets are in a scrollable section below.
- **Advanced** — Card picker for all your config option folders. Click a card to select it (turns blue). Cards with multiple sub-options open a drill-down chooser. Select All, Clear All, Apply Selected, Save Preset, Open Folder, Backup and Refresh in the bottom button row.
- **Import Config** — Browse and import external config folders directly into the toolkit directory.
- **Config Order** — Set the exact sequence in which selected configs are applied. Drag rows or use the ▲▼ buttons to reorder. Apply in Order runs the copy in your custom sequence.

### Utilities
- **APB Options** — Launch/Update, Repair Game, Uninstall APB, Reinstall APB via Steam.
- **GFAC Options** — Run GFAC Updater, Uninstall GFAC, Reinstall GFAC.
- **Other** — Open Game Folder, Open Steam, Default Target Flags shortcut creator, Advanced Target Flags dialog.

### Launch Flags
- `-nosteam` and `-nosplash / -nomovies` checkboxes live in the Advanced tab.
- Toggling either checkbox **immediately updates your existing desktop shortcut** — no need to click Play APB.
- States persist across sessions via `settings.json`.
- Shortcut creation uses your configured APB directory path, not a hardcoded `C:\` path.

### Safety
- Cards containing files that would trigger a GFAC shadowban are flagged with an amber warning.
- Apply Selected warns before copying any flagged files.
- Play APB button turns red when flagged files are selected.
- **Safe whitelist:** `.ini` `.ger` `.int` `.apb` `.txt` and `vivoxvoiceservice.exe` are never flagged.

### Settings
- **Updates** — Version card, Check for Updates, download new release, full changelog.
- **Preferences** — Dark/Light theme toggle, APB path with Save/Reset/Browse, Backup and Restore configs, Export/Import/Clear card descriptions, Reset Selections, Open Folder.

### Help
- 20+ help sections covering every feature, folder structure, troubleshooting, and flag reference — all searchable by scrolling.

---

## Requirements

- Windows 10 or 11
- PowerShell 5.1 (built into Windows — no install needed)
- APB Reloaded installed via Steam

---

## Installation

1. Download the latest release from the [Releases](https://github.com/veecfi/APB-Toolkit/releases) page.
2. Extract the folder anywhere — a dedicated folder is recommended (e.g. `C:\APB Toolkit\`).
3. Right-click `APB_Customizer.ps1` → **Run with PowerShell**.
   - If you see an execution policy error, run this once in PowerShell as Administrator:
     ```powershell
     Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
     ```
4. On first launch, go to **Advanced** and verify or set your APB Reloaded directory path, then go to **Settings → Preferences** and click **Save Path**.

---

## Folder Structure

Place your option folders directly inside the toolkit directory:

```
APB Toolkit\
  APB_Customizer.ps1
  descriptions.json
  presets.json
  settings.json
  Images\
    launch.png  repair.png  gfac.png  ...
  Backups\
  Default Preset\
    APBGame\Config\DefaultGame.ini
  Performance Mode Preset\
    APBGame\Config\DefaultEngine.ini
  My Custom Option\
    APBGame\Config\DefaultInput.ini
    Engine\Config\BaseEngine.ini
```

Each option folder must contain an `APBGame` and/or `Engine` subfolder following the APB directory structure. The toolkit copies those subfolders directly into your APB install, preserving the full relative path of every file.

---

## Adding Your Own Options

1. Create a folder next to the script (e.g. `My HUD Fix\`).
2. Inside it, replicate the APB folder structure:
   ```
   My HUD Fix\
     APBGame\Config\DefaultUI.ini
   ```
3. Click **Refresh** in the Advanced tab — your new card appears automatically.
4. Click the card to select it, then **Apply Selected**.

For multi-option configs (e.g. different colour variants), create subfolders inside your option folder. The toolkit detects them and shows a **Choose** button on the card — or just click anywhere on the card to open the chooser.

---

## Launch Flags Reference

| Flag | Effect |
|---|---|
| `-language=1031` | Loads custom localisation files (required for most configs) |
| `-nomovies` | Skips intro movies on launch |
| `-nosplash` | Skips the splash screen |
| `-nosteam` | Disables Steam integration (no overlay, no Steam login) |

These flags can be toggled from the **Advanced** tab checkboxes or the **Advanced Target Flags** dialog in Utilities → Other.

---

## Tool Card Images

Drop PNG icons into an `Images\` folder next to the script to customise Utilities tool cards:

| Filename | Card |
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

## Changelog

See the **Settings → Updates** tab inside the toolkit for the full changelog, or check the [Releases](https://github.com/veecfi/APB-Toolkit/releases) page.

**Latest: v1.4.2**
- Config Order tab with drag-to-reorder and Apply in Order
- `-nosteam` and `-nosplash/-nomovies` checkboxes with live shortcut sync
- Shortcut creation uses configured APB path (any drive)
- vivoxvoiceservice.exe and .txt files added to safe whitelist
- Preset Configs built-in section anchored, Your Presets scrollable
- Various UI fixes: rounded cards, subtle blue styling, hidden scrollbars, custom progress bar

---

## Contributing

Pull requests and issues are welcome. If you find a config file being incorrectly flagged as unsafe, open an issue with the filename and extension so it can be reviewed for the whitelist.

---

## Disclaimer

Use of modified game files is at your own risk. This tool only copies files you explicitly select. Always check what you're applying — some configs disable kiosks or streaming in ways that affect gameplay. The GFAC safe file whitelist is maintained conservatively; when in doubt, don't apply flagged files.

---

## License

MIT — see `LICENSE` for details.
