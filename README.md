<div align="center">

<img src="Icons/APBToolkit.ico" alt="APB Toolkit" width="80" />

# APB Reloaded Toolkit

**The all-in-one config manager, launcher, and maintenance tool for APB Reloaded.**

[!\[Version](https://img.shields.io/badge/version-2.1.9-blue?style=flat-square)](https://github.com/veecfi/APB-Toolkit/releases)
[!\[Platform](https://img.shields.io/badge/platform-Windows-lightgrey?style=flat-square\&logo=windows)](https://github.com/veecfi/APB-Toolkit)
[!\[PowerShell](https://img.shields.io/badge/PowerShell-5.1-blue?style=flat-square\&logo=powershell)](https://github.com/veecfi/APB-Toolkit)
[!\[License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

[**Download Latest**](https://github.com/veecfi/APB-Toolkit/releases/latest)  ·  [**Report Bug**](https://github.com/veecfi/APB-Toolkit/issues)  ·  [**Request Feature**](https://github.com/veecfi/APB-Toolkit/issues)

</div>

\---

## What is this?

APB Reloaded Toolkit is a borderless WinForms app built in PowerShell that replaces the tedious process of manually copying config files into your APB install. Select option cards, set your apply order, save presets, manage GFAC, and launch the game - all from one clean interface with full **dark and light mode** support.

No Python. No dependencies. No install. Just drop `APBToolkit.exe` in your configs folder and run.

\---

## Installation

1. Download the latest release from [**Releases**](https://github.com/veecfi/APB-Toolkit/releases/latest)
2. Extract to a dedicated folder -- e.g. `C:\\APB Toolkit\\`
3. Run `APBToolkit.exe` -- no setup, no admin rights, just launch
4. Go to **Advanced** and verify your APB path turns green, then **Settings > Preferences > Save Path**

> The download is a ready-to-run compiled `.exe` -- no PowerShell knowledge needed.

\---

## Features

<details>
<summary><b>Config Options</b></summary>

### Preset Configs

* Three built-in presets always available: **Default**, **Performance**, **High Quality**
* Save your own named presets from any selection in Advanced
* User presets show **save timestamp** in the footer
* Rename, Edit, Delete user presets from the card footer
* Built-in presets load files directly; user presets restore your card selection in Advanced

### Advanced

* Card grid showing all your option folders
* Click a card to select it (highlights blue). Cards with sub-options show a **Choose** button
* Filter by **Imported** or **Default**, search by name
* Bottom row: Apply Selected, Select All, Clear All, Save Preset, Open Folder, Clear Log, Refresh
* Activity log and progress bar track every file copied, skipped, or failed

### Import Config

* Browse and import external config folders directly into the toolkit directory
* Shows path, file count, and size before confirming

### Config Order

* Set the exact sequence configs are applied
* Drag rows to reorder, or use arrow buttons and Send to Bottom
* **Apply in Order** runs the copy in your custom sequence
* Overwrite, Backup, -nosteam, -nosplash checkboxes on the same view
* Per-file output: OK / SKIP / FAIL in the activity log

</details>

<details>
<summary><b>Utilities</b></summary>

|Tool|What it does|
|-|-|
|**APB Options**|Launch/Update, Repair, Uninstall, Reinstall APB via Steam|
|**GFAC Options**|Update, Uninstall, Reinstall GFAC anti-cheat|
|**Other**|Open game folder, open Steam, Target Flags shortcut creator|

</details>

<details>
<summary><b>Settings</b></summary>

### Updates Tab

* Hero banner card with version number, crosshair watermark, and status strip
* **Check for Updates** -- fetches latest release from GitHub
* Auto-download and relaunch on update
* Full scrollable changelog with custom scrollbar

### Preferences Tab

* **Appearance** -- Dark / Light theme toggle
* **APB Install Path** -- Browse, Save, Reset
* **Config Backup** -- Zip your APBGame\\Config with timestamp; restore from any backup zip
* **Card Descriptions** -- Export, Import, or Clear all descriptions
* **General** -- Reset selections, open script folder
* **Run on Startup** -- Adds or removes a Windows startup registry entry

</details>

<details>
<summary><b>Help Tab</b></summary>

20+ in-app help sections covering every feature -- getting started, preset configs, applying options, config order, utilities, troubleshooting, and more. Fully scrollable with a custom scrollbar.

</details>

\---

## Safety

* Cards containing files that trigger a GFAC shadowban are flagged in **crimson red**
* **Apply Selected** warns before copying any flagged files
* Play APB button turns red when flagged files are in your selection
* Safe file whitelist: `.ini` `.ger` `.int` `.apb` `.txt` `.md` and `vivoxvoiceservice.exe` are never flagged

\---

## Folder Structure

```
APB Toolkit\\
  APBToolkit.exe                  <- run this
  descriptions.json               <- auto-created
  presets.json                    <- auto-created, includes save timestamps
  settings.json                   <- auto-created
  imported\_folders.json           <- auto-created
  Images\\                         <- optional PNGs for Utilities tool cards
  Backups\\                        <- auto-created on backup
  Default Preset\\
    APBGame\\Config\\DefaultGame.ini
  Performance Mode Preset\\
    APBGame\\Config\\DefaultEngine.ini
  Your Option Folder\\
    APBGame\\Config\\DefaultInput.ini
```

> \*\*Reserved folder names\*\* (excluded from the card grid automatically):
> `Default Preset` `Performance Mode Preset` `High Quality Preset` `Backups` `Images`

\---

## Adding Your Own Options

1. Create a folder next to `APBToolkit.exe`, e.g. `My HUD Fix\\`
2. Replicate the APB folder structure inside it:

```
   My HUD Fix\\
     APBGame\\Config\\DefaultUI.ini
   ```

3. Click **Refresh** in the Advanced tab -- your card appears automatically
4. For multi-variant options (e.g. different colour choices), add subfolders:

```
   My Option\\
     Variant A\\APBGame\\Config\\...
     Variant B\\APBGame\\Config\\...
   ```

   The card will show a **Choose** button to pick between variants

   \---

   ## Getting Started

   ```
1. Run APBToolkit.exe
2. Go to Advanced -- check the directory bar turns green
3. If red, click Browse and navigate to APB Reloaded
   (usually C:\\Program Files (x86)\\Steam\\steamapps\\common\\APB Reloaded)
4. Settings > Preferences > Save Path
5. Pick your cards, click Apply Selected -- done
```

   The **Play APB** and **Update APB** buttons are always pinned to the bottom of the sidebar.

   \---

   ## Requirements

|||
|-|-|
|OS|Windows 10 or 11|
|Runtime|PowerShell 5.1 (built into Windows)|
|Game|APB Reloaded via Steam|
|Admin rights|Not required|

\---

## Changelog

<details>
<summary><b>v2.1.9 -- UI Overhaul</b> (current)</summary>

* Redesigned sidebar header with crosshair logo and gradient separator
* Custom drawn nav icons per section (grid, star, sliders, wrench, gear, circle)
* Preset Config cards redesigned: body + footer split layout, bordered badge, larger name
* Preset cards now show save timestamp in footer bar
* Preset save format updated to include `savedAt` metadata (backwards compatible)
* Updates tab: hero banner card with crosshair tile watermark, version badge, status strip
* Changelog redesigned: rounded card, custom scrollbar matching Help tab
* Flagged/unsafe cards changed from amber to crimson red
* Run on Startup added to Preferences (Windows registry `HKCU\\...\\Run`)
* Fixed vertical sidebar separator not showing on Help, Updates, Preferences tabs
* Fixed form bottom-right blue border artifact
* Fixed restore window button overlapping close button
* Fixed Update APB / Play APB button positioning in fullscreen and windowed modes
* Fixed non-ASCII bytes causing immediate crash on startup

</details>

<details>
<summary><b>v2.1.0 -- Major Release</b></summary>

* Imported/default filter pills in Advanced
* Imported folders tracked in `imported\_folders.json`
* Overwrite, Backup, -nosteam, -nosplash checkboxes in Config Order
* Config Order per-file activity log (OK/SKIP/FAIL)
* Config Order shows individual sub-option paths
* Apply in Order handles sub-option paths
* Fixed preset Load restoring all selections
* Fixed JSON type casting for arrays and booleans
* Fixed update download temp path
* Fixed window button order and disappearing after theme switch
* Fixed rounded corners, light mode, null brush crash

</details>

<details>
<summary><b>v1.5.x -- Launcher and Import</b></summary>

* Play APB closes toolkit after launching
* Update APB button above Play APB
* Import Config with folder info confirmation and conflict detection
* Auto-backup before apply
* Config Order drag, Send to Bottom, X remove, persistent order

</details>

<details>
<summary><b>v1.4.x -- Config Order</b></summary>

* Config Order tab with drag-to-reorder
* Apply in Order button
* `-nosteam` and `-nosplash/-nomovies` checkboxes (update shortcut immediately)
* PNG image support for Utilities tool cards

</details>

<details>
<summary><b>v1.0.1 - v1.3.x -- Foundation</b></summary>

* Initial release: card picker, Apply Selected, activity log, APB path detection
* Dark/light theme, GitHub update checker, Backup/Restore
* GFAC management tools
* Preset cards with Edit, Rename, Delete
* Settings and Utilities sub-navigation
* Play APB and Update APB pinned to sidebar

</details>

\---

> \*\*Disclaimer:\*\* Unofficial community tool. Not affiliated with Little Orbit or the APB Reloaded team. Always check what configs you are applying.

\---

<div align="center">

Made for the APB community  ·  [veecfi](https://github.com/veecfi)

</div>

