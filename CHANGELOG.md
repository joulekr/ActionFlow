# ActionFlow Changelog

> Format : [Keep a Changelog](https://keepachangelog.com/ko/1.0.0/)  
> Version: [Semantic Versioning](https://semver.org/lang/ko/)

---

## [0.1.8] - June 7, 2026

- **🔄 Automatic Updates**: Added automatic update functionality based on `tauri-plugin-updater`
- **🕒 Recent Tab (Recent mode)**: Added a “Recent” tab that allows you to view and search notes, clipboard items, bookmarks, and files all on a single screen
- **🗂️ Workspaces**: Added a Workspaces feature that lets you group multiple items (apps, folders, links) into a bookmark to launch them all at once

---

## [0.1.7] - 2026-06-04

- **🔢 Number System Conversion**: In default mode, entering values in the format `0xFF`, `0b11001100`, or `0o377` instantly converts them to the other three number systems
- **⭐ Recent Apps on Launcher Home Screen**: When you open the launcher without entering a search term, the top N apps based on their `usage.json` Frecency scores are displayed with a “Recently Used” label

---

## [0.1.6] - June 3, 2026

- **📋 Clipboard Type Classification (ClipType)**: Added `text`, `url`, `image`, and `file` type fields to clipboard items
- **🗄️ Clipboard Storage Switch to SQLite**: Replaced JSON files with SQLite (`clipboard.db`)
- **🪟 Search and Switch Open Windows**: When the launcher opens, it automatically fetches the list of currently open windows and displays them in the default search results
- **📁 Display File Size and Modification Date in Search Results**: Displays file size (`1.2 MB`) and modification date (`3 days ago`) in the search result subtitle
- **⭐ Newly Implemented Favorites Feature**: Expanded the existing link feature to allow favoriting various types of items, including apps and folders
- **⭐ Quickly Add to Favorites (Right-click Menu)**: In launcher mode, right-click an app → “⭐ Add to Favorites” menu appears

---

## [0.1.5] - May 31, 2026

- **🔌 Plugin `{{query}}` dynamic argument**: Text entered after the trigger is passed to the `{{query}}` placeholder in the command
- **🌐 Plugin `http` action**: Native HTTP requests without PowerShell
- **📝 Plugin `description` field**: Adds a supplementary description to display in the search result subtitle
- **🔒 Plugin `confirm` field**: When `confirm = true` is set, it requires an additional press of Enter before execution. Same UX as system commands (warning message + “OK” prompt)

---

## [0.1.4] - 2026-05-30

- **🔌 Plugin System (Custom TOML Commands)**: Define custom commands using `.toml` files in the `%APPDATA%\actionflow\plugins\` folder
- **🎨 Color Conversion**: In default mode, automatically converts inputs in `#ff0000`, `#f00`, `rgb(255, 0, 0)`, or `hsl(0, 100%, 50%)` formats to HEX, RGB, and HSL formats
- **Mode-specific blank screen guides**: Improved blank screens for each mode with specific example inputs and explanations for first-time users
- **Sort results by recent usage (Frequency)**: Saves the frequency and time of last use for apps, snippets, links, and notes in `%APPDATA%\actionflow\usage.json`
- **Improved keyboard scrolling**: In all result panels (Default, Clipboard, Snippets, Links, Emoji), if the selected item moves off-screen while scrolling ↑↓, the screen automatically scrolls
- **System Command Confirmation UX**: For `Sleep`, `Restart`, `Shut Down`, `Log Out`, `Close All Apps`, and `Empty Trash`, the command is no longer executed immediately after selecting a search result; instead, you must press Enter once more to confirm

---

## [0.1.3] - 2026-05-28

- **ℹ️ Info Panel**: Click the `ℹ` button at the far right of the mode bar to display app information (app icon, version, tech stack, developer)
- **📝 Notes Mode**: Added a new mode dedicated to notes. Enter `note`, `notes`, `memo`, or `메모`, or press Tab to enter
- **Permanent Clipboard History**: Clipboard history is retained even after the app is closed
- **Clipboard Retention Period Settings**: Select a retention period in the settings panel (7 days / 14 days / 30 days / 60 days / 90 days / Permanent; default is 30 days)
- **Set maximum number of clipboard entries**: Select the maximum number of entries in the settings panel (100 / 200 / 300 / 500 / 1000 / Unlimited, default 200)
- **Enable/Disable Modes**: You can enable or disable each mode (Clipboard / Notes / Snippets / Links / Files / Emojis) using checkboxes in the settings panel
- **Additional System Commands**: In the default mode, typing `close all apps` or `close apps` closes all visible app windows; typing `empty trash` or `empty recycle bin` empties the trash

---

## [0.1.2] - 2026-05-27

- **Emoji Dataset Expansion**: Replaced the existing static array of 970 emojis with the `emojis` crate (Unicode CLDR), now supporting search for over 3,600 emojis
- **Clipboard History**: Enter dedicated mode by typing `clip`, `clipboard`, or `history`
- **Advanced Clipboard History Features**: 📌 Pin items (pinned items always stay at the top and are excluded from bulk deletion or trimming), ✏️ Edit text inline (save with Ctrl+Enter), ⏸ Pause/resume monitoring (ignores new copied content while paused, keeps pinned items)
- **System Commands**: In standard mode, entering keywords like `lock` / `sleep` / `restart` / `shutdown` / `logout` executes them immediately
- **Timer**: Supports units such as `5m` / `1h30m`, etc.

---

## [0.1.1] - 2026-05-26

- **Quick Links**: Save frequently visited URLs by name and open them quickly
- **Calculator Function Extensions**: Supports `sin`, `cos`, `tan`, `log`, `ln`, `sqrt`, `abs`, `ceil`, and `floor` functions
- **Rearrange Snippets**: Drag the handle (`⠿`) with your mouse to change the order
- **Pin Snippets**: Pin snippets using the 📌 button. Pinned items are displayed at the top of the list
- **Data Backup/Restore**: Back up and restore all data (settings + snippets) as a JSON file from the settings panel
- **Change Global Shortcuts**: You can change shortcuts by directly entering key combinations in the settings panel
- **Select Web Search Browser**: Automatically detects all installed browsers by scanning the Windows registry

---

## [0.1.0] - 2026-05-25

### First public release. All core features of the Global Launcher have been implemented.

