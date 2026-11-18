# KRONO

**KRONO** is a minimalist, single-file, offline-first personal calendar and task planner built with vanilla HTML, CSS, and JavaScript. Designed mobile-first with a pure monochrome black-and-white glassmorphism interface, it runs directly from a single `index.html` file with zero build steps or backend dependencies.

---

## Features

### Interface & Layout
- **Mobile-First Frame:** Adapts seamlessly to mobile viewports and renders inside a centered phone frame with pure black side margins on desktop screens.
- **Monochrome Glassmorphism:** Clean black-and-white Dark and Light themes with live controls for glass opacity, backdrop blur, corner radius, and font size.
- **Adjustable Split View:** Tasks stay on the upper half and the interactive calendar stays on the lower half. Resize the split ratio via the draggable divider or Settings, and lock the ratio when desired.
- **Bilingual RTL / LTR:** Instant switching between Persian (`fa`, RTL) and English (`en`, LTR) with automatic numeral formatting.

### Triple Calendar Engine
- **Jalali, Gregorian, and Hijri Qamari:** Accurate, 100% offline date conversions with quick switching directly from the calendar header.
- **Navigation & Occasions:** Month navigation, Jump-to-Date (supporting Persian, Arabic, and Latin digits), configurable first day of the week, Hijri day offset (`-2` to `+2`), and built-in official occasions.

### Task Management
- **Automatic Overdue Rollover:** Unfinished tasks from earlier days automatically roll over to today and the following day with an **Overdue** indicator.
- **Day, Undated, and All Views:** Tap any calendar day to inspect its tasks, switch to **Undated** for backlog items, or open **All** for full offline/online access to every task across all dates.
- **Task Details:** Start and end times, priorities (`Low`, `Medium`, `High`, `Urgent`), recurring schedules (`Daily`, `Weekly`, `Monthly`, `Yearly`), internal checklists, drag-and-drop rescheduling onto calendar days, and quick search (`Ctrl+K`).

### Offline Storage & GitHub Sync
- **Offline-First Persistence:** Automatically saves all tasks and preferences in **IndexedDB** (with `localStorage` fallback) and registers a lightweight Service Worker for offline use.
- **Direct GitHub REST API Sync:** Syncs your workspace as a single JSON file in a GitHub repository. If you are offline or a sync fails, changes remain saved locally in the browser and retry automatically once connectivity returns.
- **Backup & Restore:** Export or import your data as `.json` anytime, or wipe local data from Settings.

---

## Quick Start

1. Download `index.html` into your project folder.
2. *(Optional)* Place your custom PNG icon named `favicon.png` in the same directory alongside `index.html`.
3. Open `index.html` directly in your browser, serve it on `localhost`, or deploy it to **GitHub Pages**:

```bash
# Example: serve locally for mobile testing
python3 -m http.server 8080
```

---

## GitHub Sync Setup

KRONO uses the **GitHub REST API** (`Repository Contents` endpoint) directly from your browser.

1. Create a private (or public) repository on GitHub to store your JSON data file (for example, `krono-data`).
2. In GitHub, go to **Settings → Developer settings → Personal access tokens → Fine-grained tokens** and generate a new token:
   - **Repository access:** Choose **Only select repositories** and select your data repository.
   - **Repository permissions:** Set **Contents** to **Read and write** (no other permissions are required).
3. Open **KRONO → Settings → GitHub**, enter your token, username, repository name, branch (default `main`), and file path (default `krono-tasks.json`), then click **Save** and **Test**.

> **Security Note:** Your Personal Access Token is stored strictly in your browser (`localStorage`) and is never written into the synced JSON file or exported backups.

---

## Project Structure

```text
.
├── index.html     # Complete standalone application (HTML + CSS + Modular JS)
├── favicon.png    # Optional custom app icon (user-supplied)
└── README.md      # Documentation
```

---

## Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `Ctrl + K` / `Cmd + K` | Open task search |
| `Esc` | Close active modal |

---

