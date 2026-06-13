# ActionFlow User Guide

ActionFlow is a launcher & productivity tool for Windows. With a single shortcut, you can launch apps, calculate, convert units, manage clipboard history, use snippets, search files, and more.

---

## Table of Contents

1. [Getting Started](#1-getting-started)
2. [Default Mode (Launcher)](#2-default-mode-launcher)
3. [Switching Modes](#3-switching-modes)
4. [Recent (Unified Search)](#4-recent-unified-search)
5. [Clipboard History](#5-clipboard-history)
6. [Snippets](#6-snippets)
7. [Favorites (Links)](#7-favorites-links)
8. [File Search](#8-file-search)
9. [Emoji Search](#9-emoji-search)
10. [Plugins](#10-plugins)
11. [Settings](#11-settings)
12. [Keyboard Shortcuts](#12-keyboard-shortcuts)

---

## 1. Getting Started

| Action | Method |
|--------|--------|
| Open / close launcher | `Ctrl + Shift + Space` |
| Close | `Esc` |

The search bar is focused automatically when the launcher opens — just start typing.

---

## 2. Default Mode (Launcher)

The launcher opens in default mode. Without a query, it automatically shows your most frequently used apps as a **Recent** list.

### 2-1. Launch Apps & Switch Windows

```
chrome          → Launch Chrome (or activate an open window)
excel           → Search by part of an app name
```

- Open windows appear above app results in the list.
- **Right-click** an app to add it to Favorites instantly.
- Apps you use most often rise to the top automatically (frecency-based ranking).

### 2-2. Calculator

```
2 + 3 * 4        → 14
2^10             → 1024
sqrt(16)         → 4
log(1000)        → 3   (base-10 log)
ln(1)            → 0   (natural log)
sin(pi/2)        → 1   (radians)
abs(-7)          → 7
ceil(1.2)        → 2
floor(1.9)       → 1
```

Press `Enter` on a result to copy it to the clipboard.

Supported operators: `+ − * / ^ %` and parentheses `()`  
Supported functions: `sqrt` `sin` `cos` `tan` `log` `ln` `abs` `ceil` `floor`  
Supported constants: `pi` `e`

### 2-3. Unit Conversion

```
100 km to miles  → 62.137 miles
70 kg to lbs     → 154.32 lbs
37 c to f        → 98.60 °F
1 gal to l       → 3.785 l
500 ml to fl_oz  → 16.907 fl_oz
```

Format: `number unit to unit` or `number unit in unit`

### 2-4. Currency Conversion

```
100 usd to krw   → Convert to KRW at live rate
50 eur in jpy    → EUR → JPY
1 gbp to usd     → GBP → USD
```

Uses ISO 4217 3-letter currency codes. Rates are cached for 1 hour.

### 2-5. Base Conversion

```
0xFF             → 255 (DEC) · 0b11111111 (BIN) · 0o377 (OCT)
0b11001100       → 0xCC (HEX) · 204 (DEC) · 0o314 (OCT)
255 to hex       → 0xFF
255 to bin       → 0b11111111
```

Selecting a result copies that representation to the clipboard. Supported range: 0 – 4,294,967,295 (32-bit).

### 2-6. Web Search

```
?today weather   → Open Google search
?EPL results     → Prefix ? to trigger a web search
```

### 2-7. System Resource Monitor

```
cpu              → Live CPU usage (updates every second)
ram              → RAM used / total
disk             → C: drive used / total
```

### 2-8. System Commands

> The following commands require **pressing Enter once more** to confirm.

```
lock                        → Lock screen
sleep                       → Sleep mode
close all apps              → Close all open application windows
empty trash                 → Empty the Recycle Bin
restart                     → Restart PC
shutdown                    → Shut down PC
logout                      → Log out
kill chrome / kill notepad  → Force-kill a process by name
```

### 2-9. Timer

```
timer 30s        → 30-second timer
timer 5m         → 5-minute timer
timer 1h30m      → 1 hour 30 minute timer
cancel           → Cancel the running timer
```

When the timer finishes, the launcher reappears with a green notification.

---

## 3. Switching Modes

Type `/keyword` in the search bar, or press `Tab` / `Shift+Tab` to cycle through modes.

| Input | Mode |
|-------|------|
| `/launch` or `/launcher` | ⚡ Launcher (default) |
| `/recent` | 🕒 Recent (unified search) |
| `/clip` or `/clipboard` | 📋 Clipboard history |
| `/snip` or `/snippet` | 📌 Snippets |
| `/link` or `/favorite` or `/bookmark` | ⭐ Favorites |
| `/file` or `/folder` | 📁 File search |
| `/emoji` or `/icon` | 😀 Emoji search |
| `/setting` or `/config` | ⚙️ Settings |

You can also click a mode in the mode bar at the top.

---

## 4. Recent (Unified Search)

Shows recent clipboard entries, favorites, and files in a single view.

- Without a query, the 5 most recent items from each source are shown in separate sections.
- Typing a query searches all 3 sources simultaneously and shows only sections with results.
- `Enter` acts on each item type correctly (clipboard → paste, file → open).

> File search activates after typing at least 2 characters.

---

## 5. Clipboard History

Text you copy is recorded automatically. Up to 200 entries are saved and persist across restarts.

### Actions

| Action | How |
|--------|-----|
| Paste an entry | `Enter` or click → automatically pastes into the previous window |
| Pin an entry | `📌` button → kept at the top; excluded from bulk delete |
| Edit an entry | `✏️` button → inline edit; `Ctrl+Enter` to save |
| Delete an entry | `✕` button |
| Delete all unpinned | **Clear all** button (pinned entries are preserved) |
| Pause monitoring | `⏸` button → new copies are not recorded |
| Search entries | Type in the search bar |

> Retention period and maximum entry count can be changed in Settings (defaults: 30 days, 200 entries).

---

## 6. Snippets

Save frequently used text under a trigger word and paste it instantly.

### Basic Usage

1. Enter snippet mode with `/snip`
2. Click **+ New Snippet** and fill in a trigger and content
3. In default mode, type `:trigger` to search and activate a snippet

```
:name     → paste your saved name text
:sig      → paste your email signature
:addr     → paste your address
```

> It is recommended to start triggers with `:`.

### Built-in Template Variables

Insert the following variables in snippet content — they are replaced with live values at activation time.

| Variable | Replaced with |
|----------|--------------|
| `{{today}}` | Today's date (YYYY-MM-DD) |
| `{{time}}` | Current time (HH:MM) |
| `{{datetime}}` | Date + time |
| `{{uuid}}` | Random UUID |

### Managing Snippets

| Action | How |
|--------|-----|
| Edit | `✏️` button |
| Delete | `🗑` button |
| Export | **Export** button (JSON) |
| Import | **Import** button (JSON) |

---

## 7. Favorites (Links)

Register frequently used apps, folders, links, and workspaces for one-click access.

### Adding Items

| Button | Description |
|--------|-------------|
| `+ Add App` | Pick an installed `.exe` / `.lnk` file |
| `+ Add Folder` | Pick a frequently used folder |
| `+ New Link` | Enter a name and URL manually |
| `+ Workspace` | Group multiple apps/folders/links to open at once |

> You can omit `https://` when entering a URL.

### Other Ways to Add

- **Launcher mode**: right-click an app → ⭐ Add to Favorites
- **File mode**: right-click a folder/exe/lnk → ⭐ Add to Favorites

### Managing Items

| Action | How |
|--------|-----|
| Open | `Enter` or click |
| Rename | `✏️` button |
| Delete | `🗑` button |
| Pin | `📌` button → stays at the top of the list |
| Reorder | Drag the `⠿` handle |

### Workspaces

Group multiple items and launch them all at once with a single `Enter`. Great for opening all the apps, folders, and URLs for a project in one go.

---

## 8. File Search

Search files and folders by name in your Desktop, Documents, and Downloads folders.

- Search activates after typing at least 2 characters.
- File size and modification date are shown alongside each result.

### File Mode Shortcuts

| Shortcut | Action |
|----------|--------|
| `Enter` | Open file / open folder in Explorer |
| `Space` | Toggle file preview |
| `Ctrl+C` | Copy the selected file's path to clipboard |
| `Ctrl+O` | Open the containing folder in Explorer |
| `Ctrl+Enter` | Open file properties |
| Right-click | Open folder / Copy path / Properties / ⭐ Add to Favorites |

### Search All Folders

Toggle **Search all folders** (top-left of file mode) to index every drive.

- Initial indexing may take a moment.
- System folders (Windows, Program Files, $Recycle.Bin, AppData\Temp, etc.) are excluded.
- Until indexing completes, results come from the default 3 folders (Desktop, Documents, Downloads).

---

## 9. Emoji Search

```
/emoji           → Enter emoji mode
heart            → ❤️ 🧡 💛 … related emojis
fire             → 🔥 related emojis
```

- Without a query, frequently used emojis are shown.
- `Enter` or click copies the emoji to the clipboard and pastes it into the previous window.
- Navigate the grid with `← → ↑ ↓`, select with `Enter`.

---

## 10. Plugins

Create custom commands in TOML files and run them directly from the launcher.

### Plugin Folder Location

```
%APPDATA%\actionflow\plugins\
```

Open it instantly via Settings → **Open Plugin Folder**.

> Saving a `.toml` file **reloads automatically** — no restart needed.

### Plugin File Format

```toml
[[commands]]
trigger = "google"               # trigger keyword (comma-separated aliases allowed)
name = "🔍 Google Search"        # display name in the launcher
description = "google <query>"   # optional subtitle
action = "open"                  # action type
path = "https://www.google.com/search?q={{query}}"
output = "none"
```

### Action Types

| action | Description |
|--------|-------------|
| `shell` | Run a PowerShell command (stdout → output handling) |
| `open` | Open a file, app, or URL |
| `copy` | Copy literal text to the clipboard |
| `http` | Make an HTTP GET/POST request (result → output handling) |

### Output Types

| output | Description |
|--------|-------------|
| `clipboard` | Copy the result to the clipboard |
| `paste` | Copy to clipboard then paste into the previous window |
| `none` | Execute only; ignore the result |

### Additional Options

| Option | Description |
|--------|-------------|
| `confirm = true` | Require a second `Enter` before running (for dangerous commands) |
| `timeout_secs = 10` | Execution time limit (default: 15 seconds) |
| `cwd = "C:\\path"` | Working directory for shell commands |

### Dynamic Query `{{query}}`

Text typed after the trigger is passed as `{{query}}`.

```
Input: google rust programming
→ Opens https://www.google.com/search?q=rust+programming
```

### Examples

**Copy the current time with PowerShell**
```toml
[[commands]]
trigger = "time"
name = "🕐 Current Time"
action = "shell"
command = "Get-Date -Format 'HH:mm:ss'"
output = "clipboard"
```

**Fetch weather via HTTP**
```toml
[[commands]]
trigger = "weather"
name = "🌤 Seoul Weather"
action = "http"
url = "https://wttr.in/Seoul?format=3"
output = "clipboard"
```

**Dangerous command with confirmation**
```toml
[[commands]]
trigger = "wipe temp"
name = "🗑 Clear Temp Folder"
action = "shell"
command = "Remove-Item -Path \"$env:TEMP\\*\" -Recurse -Force -ErrorAction SilentlyContinue; 'Done'"
output = "clipboard"
confirm = true
```

An `example.toml` with many ready-to-use commands is created automatically on first launch.

---

## 11. Settings

Enter via `/setting` or the ⚙️ icon in the mode bar.

| Setting | Description |
|---------|-------------|
| Language | Korean / English |
| Theme | Dark / Light / System |
| Max results | Maximum number of search results to display |
| Show icons | Show app icons in search results |
| Auto-start | Launch ActionFlow when Windows starts |
| Global shortcut | Change the launcher hotkey (click then press keys) |
| Web search browser | Browser used for web searches |
| File re-index interval | How often the file index is refreshed |
| Clipboard retention | How long clipboard history is kept (default: 30 days) |
| Clipboard max entries | Maximum number of clipboard entries to store |
| Active modes | Choose which modes appear in the mode bar |
| Backup / Restore | Back up and restore snippets, favorites, and clipboard data |
| Plugins | Open plugin folder and reload plugins |

---

## 12. Keyboard Shortcuts

### Global

| Shortcut | Action |
|----------|--------|
| `Ctrl+Shift+Space` | Open / close the launcher |
| `↑` / `↓` or `Ctrl+P` / `Ctrl+N` | Navigate items |
| `Enter` | Activate / copy to clipboard |
| `Tab` | Switch to next mode |
| `Shift+Tab` | Switch to previous mode |
| `Esc` | Close (closes preview first if open) |
| `PageDown` / `PageUp` | Move 8 items at a time |

### File Mode Only

| Shortcut | Action |
|----------|--------|
| `Space` | Toggle file preview |
| `Ctrl+C` | Copy selected file path |
| `Ctrl+O` | Open containing folder in Explorer |
| `Ctrl+Enter` | Open file properties |

### Emoji / Favorites Mode

| Shortcut | Action |
|----------|--------|
| `←` / `→` | Move left / right |
| `↑` / `↓` | Move up / down one row |
