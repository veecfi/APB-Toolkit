<div align="center">

<img src="Icons/APBToolkit.ico" alt="APB Toolkit" width="80" />

# APB Reloaded Toolkit

**The all-in-one config manager, launcher, and maintenance tool for APB Reloaded.**

[![Version](https://img.shields.io/badge/version-2.3.0-blue?style=flat-square)](https://github.com/veecfi/APB-Toolkit/releases)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey?style=flat-square&logo=windows)](https://github.com/veecfi/APB-Toolkit)
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1-blue?style=flat-square&logo=powershell)](https://github.com/veecfi/APB-Toolkit)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)
[![Discord](https://img.shields.io/badge/Discord-Join%20Server-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.gg/JjxJDys7m4)

[**Download Latest**](https://github.com/veecfi/APB-Toolkit/releases/latest) &nbsp;·&nbsp; [**Discord**](https://discord.gg/JjxJDys7m4) &nbsp;·&nbsp; [**Report Bug**](https://github.com/veecfi/APB-Toolkit/issues) &nbsp;·&nbsp; [**Request Feature**](https://github.com/veecfi/APB-Toolkit/issues)

</div>

---

## What is this?

APB Reloaded Toolkit is a borderless WinForms app built in PowerShell that replaces the tedious process of manually copying config files into your APB install. Select option cards, set your apply order, save presets, manage GFAC, and launch the game - all from one clean interface with full **dark and light mode** support.

No Python. No dependencies. No install. Just drop `APBToolkit.exe` in your configs folder and run.

---

## Installation

1. Download the latest release from [**Releases**](https://github.com/veecfi/APB-Toolkit/releases/latest)
2. Extract to a dedicated folder -- e.g. `C:\APB Toolkit\`
3. Run `APBToolkit.exe` -- no setup, no admin rights, just launch
4. Go to **Advanced** and verify your APB path turns green, then **Settings > Preferences > Save Path**

> The download is a ready-to-run compiled `.exe` -- no PowerShell knowledge needed.

---

## Features

<details>
<summary><b>Config Options</b></summary>

### Preset Configs
- Three built-in presets always available: **Default**, **Performance**, **High Quality**
- Save your own named presets from any selection in Advanced
- User presets show **save timestamp** in the footer
- Rename, Edit, Delete, reorder user presets from the card
- **Import from URL** — paste any direct link to a `presets.json` to import without downloading
- Built-in presets load files directly; user presets restore your card selection in Advanced

### Advanced
- Card grid showing all your option folders
- Click a card to select it (highlights blue). Cards with sub-options show a **Choose** button
- Filter by **Imported** or **Default**, search by name
- Bottom row: Apply Selected, Select All, Clear All, Save Preset, Open Folder, Clear Log, Refresh
- Activity log and progress bar track every file copied, skipped, or failed

### Import Config
- Browse and import external config folders directly into the toolkit directory
- Shows path, file count, and size before confirming

### Config Order
- Set the exact sequence configs are applied
- Drag rows to reorder, or use arrow buttons and Send to Bottom
- **Apply in Order** runs the copy in your custom sequence
- **Save Order** / **Load Order** — save named order presets and restore them via dropdown
- Overwrite, Backup, -nosteam, -nosplash checkboxes on the same view
- Per-file output: OK / SKIP / FAIL in the activity log

</details>

<details>
<summary><b>Utilities</b></summary>

| Tool | What it does |
|------|-------------|
| **APB Options** | Launch/Update, Repair, Uninstall, Reinstall APB via Steam |
| **GFAC Options** | Update, Uninstall, Reinstall GFAC anti-cheat |
| **Other** | Open game folder, open Steam, Target Flags shortcut creator |

</details>

<details>
<summary><b>Settings</b></summary>

### Updates Tab
- Hero banner card with version number, crosshair watermark, and status strip
- **Check for Updates** -- fetches latest release from GitHub
- Auto-download and relaunch on update
- Full scrollable changelog with custom scrollbar

### Preferences Tab
- **Appearance** -- Dark / Light theme toggle (also accessible via moon/sun icon in the header)
- **APB Install Path** -- Browse, Save, Reset
- **Config Backup** -- Zip your APBGame\Config with timestamp; restore from any backup zip
- **Card Descriptions** -- Export, Import, or Clear all descriptions
- **General** -- Reset selections, open script folder
- **Run on Startup** -- Adds or removes a Windows startup registry entry
- **Usage Statistics** -- Opt-in anonymous telemetry (version + actions only)

</details>

<details>
<summary><b>Help Tab</b></summary>

20+ in-app help sections covering every feature -- getting started, preset configs, applying options, config order, utilities, troubleshooting, and more. Fully scrollable with a custom scrollbar.

</details>

---

## Safety

- Cards containing files that trigger a GFAC shadowban are flagged in **crimson red**
- **Apply Selected** warns before copying any flagged files
- Play APB button turns red when flagged files are in your selection
- Safe file whitelist: `.ini` `.ger` `.int` `.apb` `.txt` `.md` and `vivoxvoiceservice.exe` are never flagged

---

## Folder Structure

```
APB Toolkit\
  APBToolkit.exe                  <- run this
  descriptions.json               <- auto-created
  presets.json                    <- auto-created, includes save timestamps
  settings.json                   <- auto-created
  order_presets.json              <- auto-created when you save an order preset
  imported_folders.json           <- auto-created
  Images\                         <- optional PNGs for Utilities tool cards
  Backups\                        <- auto-created on backup
  Default Preset\
    APBGame\Config\DefaultGame.ini
  Performance Mode Preset\
    APBGame\Config\DefaultEngine.ini
  Your Option Folder\
    APBGame\Config\DefaultInput.ini
```

> **Reserved folder names** (excluded from the card grid automatically):
> `Default Preset` `Performance Mode Preset` `High Quality Preset` `Backups` `Images`

---

## Adding Your Own Options

1. Create a folder next to `APBToolkit.exe`, e.g. `My HUD Fix\`
2. Replicate the APB folder structure inside it:
   ```
   My HUD Fix\
     APBGame\Config\DefaultUI.ini
   ```
3. Click **Refresh** in the Advanced tab -- your card appears automatically
4. For multi-variant options (e.g. different colour choices), add subfolders:
   ```
   My Option\
     Variant A\APBGame\Config\...
     Variant B\APBGame\Config\...
   ```
   The card will show a **Choose** button to pick between variants

---

## Getting Started

```
1. Run APBToolkit.exe
2. Go to Advanced -- check the directory bar turns green
3. If red, click Browse and navigate to APB Reloaded
   (usually C:\Program Files (x86)\Steam\steamapps\common\APB Reloaded)
4. Settings > Preferences > Save Path
5. Pick your cards, click Apply Selected -- done
```

The **Play APB** and **Update APB** buttons are always pinned to the bottom of the sidebar.

---

## Requirements

| | |
|---|---|
| OS | Windows 10 or 11 |
| Runtime | PowerShell 5.1 (built into Windows) |
| Game | APB Reloaded via Steam |
| Admin rights | Not required |

---

## Changelog

<details>
<summary><strong>v2.3.0</strong> — Current</summary>

**UI Improvements**
- Update notification banner — shows across all tabs when a new version is available, click to update, dismiss with X
- Confirmation dialog before Apply Selected showing the full list of options that will be applied
- Auto-backup before every apply — zips `APBGame\Config` to Backups folder with timestamp automatically
- Preset import from URL — paste any direct link to a `presets.json` (GitHub raw, Discord CDN) to import instantly
- Fuzzy search on option cards — partial/out-of-order matching with accent-highlighted matched text
- Hover tooltip on option cards — 600ms delay then shows the card's description in a floating panel
- Recently applied section on Advanced tab — last 5 apply sessions with timestamp and option names
- Preset reordering — up/down arrow buttons on every user preset card
- Light/dark mode toggle button in the header bar (moon/sun icon) for instant switching
- Animated tab transitions — accent sweep line plays across content area top on every nav click
- Settings panel redesigned — glass gradient cards, cleaner section headers, tighter spacing
- Config Order save/load presets — save named order presets and restore them via dropdown (`order_presets.json`)

**Discord Bot**
- Official Discord bot launched with `/download`, `/changelog`, `/version`, `/apbstatus`, `/stats`, `/share`, `/getpreset`
- New commands: `/bug` modal form, `/compare`, `/random`, `/mypresets`, `/leaderboard`, `/setup`
- GitHub webhook — new releases auto-post to `#latest-release` with download embed
- Weekly stats digest — every Monday posts active users, version chart, top options to `#stats`
- Staff thread commands — `!fix`, `!investigating`, `!wontfix`, `!duplicate` update bug report status
- Auto-welcome DM — new members receive a quick start guide on join
- Milestone announcements — bot posts when toolkit hits 100, 500, 1000+ downloads
- Opt-in usage statistics — anonymous telemetry viewable via `/stats`

</details>

<details>
<summary><strong>v2.2.5</strong></summary>

- Discord sidebar card with live member and online counts via invite API
- Discord bot launched — `/download`, `/changelog`, `/version`, `/apbstatus`, `/stats`, `/share`, `/getpreset`
- GitHub webhook integration — new releases auto-post to Discord
- Preset sharing via Discord bot — upload `presets.json`, bot formats and posts to showcase
- Opt-in usage statistics — anonymous telemetry to bot database, viewable via `/stats`
- Run on Startup preference added to Settings
- Fixed Discord card rendering artifacts and icon cutoff at all DPI scales
- Fixed stat pill widths to dynamically size around any text length
- Fixed button spacing consistency across all layout handlers

</details>


<details>
<summary><b>v2.1.9 -- UI Overhaul</b> (current)</summary>

- Redesigned sidebar header with crosshair logo and gradient separator
- Custom drawn nav icons per section (grid, star, sliders, wrench, gear, circle)
- Preset Config cards redesigned: body + footer split layout, bordered badge, larger name
- Preset cards now show save timestamp in footer bar
- Preset save format updated to include `savedAt` metadata (backwards compatible)
- Updates tab: hero banner card with crosshair tile watermark, version badge, status strip
- Changelog redesigned: rounded card, custom scrollbar matching Help tab
- Flagged/unsafe cards changed from amber to crimson red
- Run on Startup added to Preferences (Windows registry `HKCU\...\Run`)
- Fixed vertical sidebar separator not showing on Help, Updates, Preferences tabs
- Fixed form bottom-right blue border artifact
- Fixed restore window button overlapping close button
- Fixed Update APB / Play APB button positioning in fullscreen and windowed modes
- Fixed non-ASCII bytes causing immediate crash on startup

</details>

<details>
<summary><b>v2.1.0 -- Major Release</b></summary>

- Imported/default filter pills in Advanced
- Imported folders tracked in `imported_folders.json`
- Overwrite, Backup, -nosteam, -nosplash checkboxes in Config Order
- Config Order per-file activity log (OK/SKIP/FAIL)
- Config Order shows individual sub-option paths
- Apply in Order handles sub-option paths
- Fixed preset Load restoring all selections
- Fixed JSON type casting for arrays and booleans
- Fixed update download temp path
- Fixed window button order and disappearing after theme switch
- Fixed rounded corners, light mode, null brush crash

</details>

<details>
<summary><b>v1.5.x -- Launcher and Import</b></summary>

- Play APB closes toolkit after launching
- Update APB button above Play APB
- Import Config with folder info confirmation and conflict detection
- Auto-backup before apply
- Config Order drag, Send to Bottom, X remove, persistent order

</details>

<details>
<summary><b>v1.4.x -- Config Order</b></summary>

- Config Order tab with drag-to-reorder
- Apply in Order button
- `-nosteam` and `-nosplash/-nomovies` checkboxes (update shortcut immediately)
- PNG image support for Utilities tool cards

</details>

<details>
<summary><b>v1.0.1 - v1.3.x -- Foundation</b></summary>

- Initial release: card picker, Apply Selected, activity log, APB path detection
- Dark/light theme, GitHub update checker, Backup/Restore
- GFAC management tools
- Preset cards with Edit, Rename, Delete
- Settings and Utilities sub-navigation
- Play APB and Update APB pinned to sidebar

</details>

---

## Discord Bot

The official APB Toolkit Discord bot is live on the server. Available commands:

| Command | Description |
|---|---|
| `/download` | Latest release with download link |
| `/changelog` | Recent changelogs |
| `/version` | Check if you're up to date |
| `/apbstatus` | APB server status + live player count |
| `/stats` | Toolkit usage statistics |
| `/share` | Share a preset from your `presets.json` |
| `/getpreset <id>` | Download a shared preset |
| `/compare <a> <b>` | Diff two shared presets |
| `/random` | Get a random community preset |
| `/mypresets` | Your shared presets and download counts |
| `/leaderboard` | Most applied options and downloaded presets |
| `/bug` | Submit a bug report via modal form |

**Join the server:** [discord.gg/JjxJDys7m4](https://discord.gg/JjxJDys7m4)

---

> **Disclaimer:** Unofficial community tool. Not affiliated with Little Orbit or the APB Reloaded team. Always check what configs you are applying.

---

<div align="center">

Made for the APB community &nbsp;·&nbsp; [veecfi](https://github.com/veecfi) &nbsp;·&nbsp; [Discord](https://discord.gg/JjxJDys7m4)

</div>
