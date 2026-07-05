# ActionFlow User Guide

ActionFlow is a launcher & productivity tool for Windows. With a single shortcut, you can launch apps, calculate, convert units, manage clipboard history, use snippets, search files, and more.

---

## Table of Contents

1. [Getting Started](#1-getting-started)
2. [Default Mode (All)](#2-default-mode-all)
3. [Switching Modes](#3-switching-modes)
4. [Clipboard History](#4-clipboard-history)
5. [Snippets](#5-snippets)
6. [Favorites (Links)](#6-favorites-links)
7. [File Search](#7-file-search)
8. [Emoji Search](#8-emoji-search)
9. [Plugins](#9-plugins)
10. [Settings](#10-settings)
11. [Keyboard Shortcuts](#11-keyboard-shortcuts)

---

## 1. Getting Started

| Action | Method |
|--------|--------|
| Open / close launcher | `Ctrl + Shift + Space` |
| Close | `Esc` |

The search bar is focused automatically when the launcher opens — just start typing.

---

## 2. Default Mode (All)

The launcher opens in default mode. Without a query, it automatically shows your most frequently used apps as a **Recent** list.

### 2-0. Hybrid Unified Search

When you type a query, results aren't limited to apps and the calculator anymore — **snippets, clipboard history, favorites, and files (2+ characters)** are searched in parallel and merged into a single ranked list, sorted by exact match, frecency, and per-kind priority.

- Mixed-in results are still distinguishable by their kind icon (📌 snippet · 📋 clipboard · ⭐ favorite · 📁 file).
- To narrow to one source, click a mode tab or use a keyword filter like `clip:` or `snippet:`.
- Right-click still gives you actions (run, delete, etc.) directly, without switching to the dedicated tab.

### 2-1. Launch Apps & Switch Windows

```
chrome          → Launch Chrome (or activate an open window)
excel           → Search by part of an app name
```

- Open windows appear above app results in the list.
- **Right-click** an app for options like adding it to Favorites or running as administrator.
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
| `/all` or `/launch` | ⚡ All (default) |
| `/clip` or `/clipboard` | 📋 Clipboard history |
| `/snip` or `/snippet` | 📌 Snippets |
| `/link` or `/favorite` or `/bookmark` | ⭐ Favorites |
| `/file` or `/folder` | 📁 File search |
| `/emoji` or `/icon` | 😀 Emoji search |
| `/setting` or `/config` | ⚙️ Settings |

You can also click a mode in the mode bar at the top.

---

## 4. Clipboard History

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

### Extract Text from Images (OCR)

Selecting an image clip shows a **🔎 OCR** button in the detail panel.

- Clicking it recognizes text in the image using the built-in Windows OCR engine (no separate install or download needed).
- The recognized text appears below the preview, with a **Copy** button to copy it to the clipboard directly.
- If no OCR language pack is installed for your language, an instructional message appears along with an **⚙️ Open Language Settings** button, which opens the Windows Settings "Language & region" page directly.

---

## 5. Snippets

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

## 6. Favorites (Links)

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

- **All mode**: right-click an app → ⭐ Add to Favorites
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

## 7. File Search

Search files and folders by name in your Desktop, Documents, and Downloads folders.

- Search activates after typing at least 2 characters.
- File size and modification date are shown alongside each result.
- Thanks to hybrid unified search, file results also appear in Default mode, and preview works there too.

### File Preview

Press `Ctrl+P` to open a preview column beside the result list (the window widens to fit both).

- Text files show the first 10 lines, with syntax highlighting for JSON, Markdown, and code (TS, JS, Rust, Python, etc.).
- Image files are scaled to fill the preview area.
- Close the preview with `Esc` or the close (✕) button.

### File Mode Shortcuts

| Shortcut | Action |
|----------|--------|
| `Enter` | Open file / open folder in Explorer |
| `Ctrl+P` | Toggle file preview (shown beside the list) |
| `Ctrl+C` | Copy the selected file's path to clipboard |
| `Ctrl+O` | Open the containing folder in Explorer |
| `Ctrl+Enter` | Open file properties |
| `Ctrl+Shift+Enter` | Run as administrator |
| Right-click | Open folder / Copy path / Properties / Run as administrator / ⭐ Add to Favorites |

### Search All Folders

Toggle **Search all folders** (top-left of file mode) to index every drive.

- Initial indexing may take a moment.
- System folders (Windows, Program Files, $Recycle.Bin, AppData\Temp, etc.) are excluded.
- Until indexing completes, results come from the default 3 folders (Desktop, Documents, Downloads).

---

## 8. Emoji Search

```
/emoji           → Enter emoji mode
heart            → ❤️ 🧡 💛 … related emojis
fire             → 🔥 related emojis
```

- Without a query, frequently used emojis are shown.
- `Enter` or click copies the emoji to the clipboard and pastes it into the previous window.
- Navigate the grid with `← → ↑ ↓`, select with `Enter`.

---

## 9. Plugins

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

### Built-in Example Plugins (example.toml)

Below is the full list of commands included in the `example.toml` file that is generated on first launch.

#### 🔍 Dynamic Search

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `google` | 🔍 Google Search | Search Google for a keyword | `google react hooks` → opens Google in browser |
| `yt` | ▶ YouTube Search | Search YouTube for a keyword | `yt lo-fi music` → opens YouTube results |
| `naver` | 🔍 Naver Search | Search Naver for a keyword | `naver weather` → opens Naver search |
| `papago` | 🌐 Papago Translate | Open Papago translation page | `papago hello world` → opens translation result |

#### 🤖 AI Search

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `gpt` | 🤖 ChatGPT | Send a question to ChatGPT | `gpt how to sort in python` → opens ChatGPT |
| `perplexity` | 🔎 Perplexity | Search with Perplexity AI | `perplexity tauri v2` → opens Perplexity search |

#### 🌤 HTTP Request

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `weather` | 🌤 Seoul Weather | Fetch one-line Seoul weather from wttr.in | `weather` → copies weather info to clipboard |

#### 📅 Date & Time

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `date` | 📅 Today's Date | Today's date in yyyy-MM-dd | `date` → copies `2026-06-14` to clipboard |
| `time` | 🕐 Current Time | Current time in HH:mm:ss | `time` → copies `14:30:22` to clipboard |
| `datetime` | 📅 Date + Time | Date and time combined | `datetime` → copies `2026-06-14 14:30:22` to clipboard |
| `timestamp` | ⏱ Unix Timestamp | Current Unix timestamp (seconds) | `timestamp` → copies `1749912622` to clipboard |
| `week` | 📆 Week Number | ISO week number of the current week | `week` → copies `24` to clipboard |

#### 🌐 Network

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `ip` | 🌐 Public IP | Your internet-facing public IP address | `ip` → copies `203.xxx.xxx.xxx` to clipboard |
| `local ip` | 🔌 Local IP | LAN IP address of this machine | `local ip` → copies `192.168.1.xxx` to clipboard |

#### 🔑 Generate

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `uuid` | 🔑 Generate UUID | Random UUID v4 | `uuid` → copies `f47ac10b-...` to clipboard |
| `password` | 🔐 Random Password (16 chars) | Uppercase, lowercase, digits, and special chars | `password` → copies `aB3#xK9!...` to clipboard |
| `random` | 🎲 Random Number (1–100) | Random integer between 1 and 100 | `random` → copies `42` to clipboard |

#### 💻 System Info

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `user` | 👤 Current Username | Windows login username | `user` → copies `joule` to clipboard |
| `hostname` | 💻 Computer Name | Hostname of this PC | `hostname` → copies `DESKTOP-XXXXX` to clipboard |
| `uptime` | ⏰ System Uptime | Time elapsed since last boot | `uptime` → copies `3 days 2 hours 15 minutes` to clipboard |
| `disk` | 💾 C: Drive Space | Free and total capacity of C: drive | `disk` → copies `Free: 123.4 GB / Total: 500.0 GB` to clipboard |

#### 📁 Open Folder

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `open downloads` | 📥 Downloads Folder | Open user's Downloads folder | `open downloads` → opens in Explorer |
| `open desktop` | 🖥 Desktop Folder | Open user's Desktop folder | `open desktop` → opens in Explorer |
| `open docs` | 📄 Documents Folder | Open user's Documents folder | `open docs` → opens in Explorer |
| `open appdata` | 📁 AppData Folder | Open roaming AppData folder | `open appdata` → opens in Explorer |
| `open plugins` | 🔌 Plugins Folder | Open ActionFlow's plugin folder | `open plugins` → opens in Explorer |

#### ⚠️ Dangerous Commands (requires Enter confirmation)

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `wipe temp` | 🗑 Clear Temp Folder | Delete all user temporary files | `wipe temp` → Enter → Enter again to confirm |

#### 📡 Other

| Trigger | Name | Description | Usage |
|---------|------|-------------|-------|
| `ping` | 📡 Ping Google (×3) | Ping 8.8.8.8 three times | `ping` → copies ping result to clipboard (10s timeout) |
| `hello` | 👋 Paste Greeting | Paste a saved greeting into the previous window | `hello` → pastes `안녕하세요! 반갑습니다 😊` |

---

## 10. Settings

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

## 11. Keyboard Shortcuts

### Global

| Shortcut | Action |
|----------|--------|
| `Ctrl+Shift+Space` | Open / close the launcher |
| `↑` / `↓` or `Ctrl+P` / `Ctrl+N` | Navigate items |
| `Enter` | Activate / copy to clipboard |
| `Ctrl+Shift+Enter` | Run an app/file as administrator |
| `Tab` | Switch to next mode |
| `Shift+Tab` | Switch to previous mode |
| `Esc` | Close (closes preview first if open) |
| `PageDown` / `PageUp` | Move 8 items at a time |

### File Mode Only

| Shortcut | Action |
|----------|--------|
| `Ctrl+P` | Toggle file preview (shown beside the list) |
| `Ctrl+Shift+Enter` | Run as administrator |
| `Ctrl+C` | Copy selected file path |
| `Ctrl+O` | Open containing folder in Explorer |
| `Ctrl+Enter` | Open file properties |

### Emoji / Favorites Mode

| Shortcut | Action |
|----------|--------|
| `←` / `→` | Move left / right |
| `↑` / `↓` | Move up / down one row |
