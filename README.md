# ActionFlow
Windows Launcher &amp; Productivity Tool in rust

---

## 1. Project Overview

| Item | Description |
|------|------|
| Platform | Windows 10/11 only |
| Backend | Rust (Tauri v2) |
| Frontend | React 18 + TypeScript + Vite |
| Global Shortcut | `Ctrl + Shift + Space` (can be changed in settings) |
| Deployment Format | NSIS Installer (`.exe`) |
| Data Storage | `%APPDATA%\actionflow\` (mixed JSON + SQLite) |
| Language | English, Korean |

---

## 2. Mode System

9 modes. Cycle through them using `Tab` / `Shift+Tab`, or enter `/keyword` in the search bar to switch directly.

| Mode | Tab Order | Entry Keyword | Description |
|------|---------|------------|------|
| `default` | 1 | `launcher` / `launch` | Apps, Calculator, Conversion, Web Search |
| `recent` | 2 | `recent` | Combined view of recent clips, bookmarks, and files |
| `clipboard` | 3 | `clip` / `clipboard` | Clipboard history |
| `snippet` | 4 | `snippet` / `snip` | Snippet list |
| `links` | 5 | `link` / `bookmark` | Bookmarks + Workspace |
| `files` | 6 | `file` / `folder` | File search |
| `emoji` | 7 | `emoji` / `icon` | Emoji search |
| `settings` | 8 | `settings` / `config` | Settings panel |
| `help` | 9 | `help` | Help panel |

Use the ℹ button on the ModeBar to display the About panel inline (no mode change).

---

## 3. Keyboard Navigation

| Key | Action |
|----|------|
| `↑` / `↓` | Move to select an item (Emoji and Favorites move by row) |
| `←` / `→` | Move left/right in the emoji/favorites grid |
| `PageDown` / `PageUp` | Move in increments of 8 items |
| `↵ Enter` | Execute selected item / Copy to clipboard |
| `Ctrl+Enter` | Open file properties window |
| `Ctrl+C` | Copy file path to clipboard |
| `Ctrl+O` | Open folder containing the file |
| `Esc` | Close window (Closes About or Risk Confirmation window first if open) |
| `Tab` / `Shift+Tab` | Cycle through next/previous mode |

---

## 4. Key Features

### 4.1 App Launch Search
- Scans: Start Menu (User and Public), Program Files, `shell:AppsFolder` (UWP/Store apps), Control Panel CLSID entries

### 4.2 Inline Calculator
- Pure Rust recursive descent parser (no external crates)

### 4.3 Unit Conversion
- Pattern: `<number> <unit> to/in <unit>`

### 4.4 Web Search
- Enter `?` at the end of the input → Performs a Google search using the default browser

### 4.5 Snippets
- `SnippetStore`: `Mutex<Vec<SnippetEntry>>` + `snippets.json` persistence

### 4.6 Clipboard History
- Win32 `OpenClipboard` / `GetClipboardData`

### 4.7 Favorites (Links) + Workspace
- `LinkEntry`: Supports app, folder, and URL types; extracts actual icons

### 4.8 File Search
- **Quick Search**: 4-level navigation through Desktop / Documents / Downloads (ready to use)
- **Full-text Search**: SQLite indexing of drives C through Z

### 4.9 Emoji Search
- `emojis` crate (Unicode CLDR 3,600+ emojis)

### 4.10 Plugin System
- Define custom commands using `.toml` files in the `%APPDATA%\actionflow\plugins\` folder

### 4.11 Timer
- Parses English and Korean units such as `5m` / `1h30m` / `30 seconds` / `1 hour`

### 4.12 System Commands
- `lock` · `sleep` · `restart` · `shutdown` · `logout` · `close all apps` · `empty trash`

### 4.13 Switching Between Open Windows
- Collect a list of currently open windows using `EnumWindows` + `QueryFullProcessImageNameW`

### 4.14 Sorting by Usage Frequency (Frecency)
- `UsageStore`: `Mutex<HashMap<key, UsageEntry>>` + `usage.json`

### 4.15 Recent Items Mode (Recent)
- Integrated view of clipboard, favorites, and files on a single screen

### 4.16 Automatic Updates
- Based on `tauri-plugin-updater`, with minisign signature verification

---

## 5. Feature list:
### Finished:
[ ] - 

### Planned:
[ ] - 

---

Copyright (c) 2026 Joule Jang

All rights reserved.

No permission is granted to use, copy, modify,
merge, publish, distribute, sublicense, or sell
copies of this software without explicit permission
from the copyright holder.
