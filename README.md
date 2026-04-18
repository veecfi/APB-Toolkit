# APB Reloaded Toolkit

**Version 2.1.9**  
A all-in-one configuration, launch, and maintenance tool for APB Reloaded.

---

## What It Does

APB Reloaded Toolkit lets you manage your APB config files, apply preset configurations, maintain your install, and launch the game — all from one clean sidebar-driven interface. No manual file copying, no digging through folders.

---

## Features

### Config Options
- **Import Config** — Import a config folder directly into your APB directory with conflict detection and optional backup
- **Preset Configs** — Save and load named presets of your selected options. Built-in presets (Default, Performance, High Quality) are always available. User presets show save timestamps and support rename, edit, and delete
- **Advanced** — Browse all available option cards, select what you want, and apply them. Multi-option cards support sub-selection. Filter by imported/default and search by name
- **Config Order** — Set the order configs are applied. Drag to reorder, use arrow buttons, send to bottom. Apply in Order respects the sequence

### Utilities
- **APB Options** — Launch APB, trigger Steam update check, repair install, uninstall/reinstall
- **GFAC Options** — Manage GFAC anti-cheat: update, uninstall, reinstall
- **Other** — Target flags, shortcut creator, additional utilities

### Settings
- **Updates** — Check for new toolkit versions, view changelog
- **Preferences** — Toggle dark/light theme, set APB install path, backup/restore config files, export/import card descriptions, reset selections, run on startup toggle

### Help
- Full in-app documentation covering every feature

---

## Getting Started

1. Open the toolkit and go to **Advanced**
2. Check the APB Reloaded Directory path at the top — it turns green if valid, red if not found
3. If red, click **Browse** and navigate to your APB install folder (usually `C:\Program Files (x86)\Steam\steamapps\common\APB Reloaded`)
4. Go to **Settings > Preferences** and click **Save Path** so it loads automatically next time
5. The **Play APB** button is always visible at the bottom-left of the sidebar

---

## Usage

### Applying Config Options
1. Go to **Config Options > Advanced**
2. Click cards to select them (they highlight blue). Cards with multiple sub-options show a **Choose** button
3. Click **Apply Selected** to copy the files to your APB directory
4. The activity log shows every file copied, skipped, or failed
5. The progress bar tracks overall progress

### Saving a Preset
1. Select the options you want in Advanced
2. Click **Save Preset** in the bottom button row
3. Give it a name and click Save
4. It appears under **Your Presets** in Preset Configs with a save timestamp

### Loading a Preset
- **Built-in presets** — Click Load to confirm, then files are copied immediately to APB
- **User presets** — Click Load to select the matching cards in Advanced, then click Apply Selected

### Run on Startup
Go to **Settings > Preferences** and click **Enable** on the Run on Startup card. The toolkit will launch automatically when Windows starts. Click again to disable.

---

## File Structure

```
APB_Customizer.ps1          # Main script
presets.json                # Saved user presets (auto-created)
descriptions.json           # Card descriptions (auto-created)
imported_folders.json       # Tracked imported folders (auto-created)
settings.json               # App settings (auto-created)
[Option Folders]/           # Config option subfolders (APBGame/, Engine/ inside)
Default Preset/             # Built-in preset folder
Performance Mode Preset/    # Built-in preset folder
High Quality Preset/        # Built-in preset folder
Images/                     # Optional PNG images for Utilities tool cards
```

---

## Changelog

### v2.1.9
- Major UI overhaul
- Redesigned sidebar header with crosshair logo and gradient separator
- Custom drawn nav icons per section (grid, star, sliders, wrench, gear, circle-?)
- Preset Config cards redesigned with body/footer split layout, badge border, larger name
- Preset cards now show save timestamp in footer
- Preset save format updated to include savedAt metadata (backwards compatible)
- Hero banner card on Updates tab with crosshair watermark, version badge, status strip
- Changelog box redesigned with rounded card and custom scrollbar matching Help tab
- Flagged/unsafe cards changed from amber to crimson red for clearer danger indication
- Run on Startup option added to Preferences
- Fixed vertical sidebar separator line not showing on Help, Updates, Preferences tabs
- Fixed form bottom-right blue border artifact
- Fixed restore window button overlapping close button
- Fixed Update APB and Play APB button positioning in fullscreen and windowed modes
- Fixed non-ASCII bytes in script causing immediate crash on startup

### v2.1.0
- Major release
- Added imported/default filter pills to Advanced tab
- Imported folders tracked in imported_folders.json on import
- Added Overwrite, Backup, -nosteam, -nosplash checkboxes to Config Order tab
- Config Order activity log shows full file copy output (OK/SKIP/FAIL per file)
- Config Order list shows individual sub-option paths
- Apply in Order expanded to handle sub-option paths directly
- Preset configs now shows option count only
- Fixed preset Load not restoring all selections
- Fixed JSON type casting for arrays and booleans
- Fixed update download path to avoid file-in-use error
- Fixed update bat file sequence
- Fixed window button order: Min / Max / Close
- Fixed window buttons disappearing after theme switch
- Fixed rounded button corner rectangles
- Fixed light mode coverage across all panels
- Fixed null brush crash on startup
- Fixed Edit Description double-click to close
- Fixed sub-option cards showing folder path as description fallback

### v1.5.5
- Play APB closes toolkit after launching
- Launch/Update, Repair, Update APB now use APBLauncher.exe directly
- GFAC Uninstall/Reinstall also deletes TPI folder
- Added imported/preset filter pills and text search to Advanced
- Fixed null brush crash on startup
- Fixed window button issues

### v1.5.1 - v1.5.4
- Update APB button added above Play APB
- Config Order send-to-bottom, X remove button, drag improvements
- Import Config redesigned with folder info confirmation
- Conflict detection for overlapping config files
- Auto-backup before apply when enabled
- Various bug fixes

### v1.4.2
- Config Order tab with drag-to-reorder
- Apply in Order button
- -nosteam and -nosplash/-nomovies checkboxes
- Preset Config built-in presets anchored, user presets scrollable

### v1.2.9 - v1.3.0
- Preset card Edit and Rename buttons
- Delete confirmation dialog
- PNG image support for Utilities tool cards
- Play APB button pinned to sidebar
- Update APB button
- Scrollable changelog card
- Settings sub-navigation (Updates / Preferences)
- Utilities sub-navigation (APB Options / GFAC Options / Other)

### v1.0.1 - v1.2.0
- Initial public release
- Config options card picker with multi-option support
- Apply Selected copies files to APB directory
- Activity log, APB path auto-detection
- Dark/light theme toggle
- GitHub update checker
- Backup and restore
- GFAC management tools

---

## Requirements

- Windows 10 or 11
- PowerShell 5.1 or later
- APB Reloaded installed via Steam

## Running the Script

Right-click `APB_Customizer.ps1` and select **Run with PowerShell**, or run from a PowerShell terminal:

```powershell
powershell -ExecutionPolicy Bypass -File "APB_Customizer.ps1"
```

---

*APB Reloaded Toolkit is an unofficial community tool and is not affiliated with Little Orbit or the APB Reloaded development team.*
