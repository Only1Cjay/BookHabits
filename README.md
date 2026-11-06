# BookHabits

**Habits X Book Routine Tracker** — a simple tracker that pairs daily habits with a reading routine.

BookHabits is a single-file web app (PWA) built by a PharmD student to keep a daily habit routine and a book-reading routine in one place. It installs on your phone like a native app and works offline, so the routine is always at hand.

## Features

- **Two tabs — Habits and Books** — daily habit routines and a book list live in one app.
- **Habit routines** — create routines (e.g. a morning routine) and add tasks inside each one; rename routines and tasks by tapping their names, or delete them. Tick tasks off each day, and the app rolls over to a new day automatically at midnight. Each routine card shows a done/total counter with a percentage and a 7-day strip of completion rings (one arc per day, today's ring showing its count).
- **Habit history and stats** — per-routine completion percentages for the last 7, 30, and 90 days, shown with a 30-day heatmap grid (one shaded cell per day). Found in the menu on the Habits tab.
- **Book list** — add books with title (required), author, genre (free text with 12 preset suggestions), status (To Read / Reading / Completed — new books default to Reading), start and finish dates, notes/quotes (up to 800 characters), and a 1–5 star rating. Books can be edited or deleted from the same form.
- **Search and filter books** — search across title, author, and notes; filter by genre or status; and sort by title, author, rating, finish date, or date added.
- **Google Drive sync** — optional sync to a Drive folder (`BookHabits`, file `cjay-bookhabits.json`) with your own Google OAuth Client ID — the same client ID is shared with CjayNotes. Push, Pull, and a choice to merge with or replace the data on your device (Merge adds only cloud items not already on the device; Replace wipes local data first). A last-synced line is shown in Settings, and Restore from Drive is offered on the empty Habits screen when a client ID is set.
- **JSON backup and restore** — export all data as a JSON backup file (`cjay-bookhabits-backup-<date>.json`) and import it back.
- **Dark / light theme** — a theme toggle in the header switches between light and dark mode; the choice is remembered on the device.
- **History and Settings** — habit history and app settings live in the menu; Settings also has a danger zone with a Clear all data button (confirmed before wiping).
- **Installable (PWA)** — add it to your home screen; it opens standalone with its own icon and a blue (`#1a7ab0`) theme colour.
- **Offline-first** — a service worker caches the app so it loads and works without internet.

## How to use

1. Open `index.html` in a browser.
2. Use the floating `+` button to add a routine (Habits tab) or a book (Books tab), then follow the on-screen tracker to mark your habits and reading for the day.
3. To install it on your phone, use your browser's "Add to Home Screen" option.

No account, build step or installation is needed — the whole app lives in a single `index.html` file. Just open it (or serve the folder with any static file server) and it runs.

## Tech stack

- Plain HTML, CSS and JavaScript in a single file — no framework, no build step.
- [Font Awesome 6.0.0-beta3](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css) icons (CDN).
- Google Fonts: Inter.
- Service Worker (`sw.js`, cache version `v1.1.3`) with stale-while-revalidate caching for the app and cache-first for fonts/icons.
- Web App Manifest (`manifest.json`) — standalone display.

## Project structure

```
BookHabits/
├── index.html    # The entire app: markup, styles and logic in one file (~73 KB, 1,840 lines)
├── sw.js         # Service worker: offline cache
├── manifest.json # PWA manifest (name, icons, theme colour)
├── icon.svg      # App icon
└── README.md     # Previously just: "Habits X Book Routine Tracker"
```

## Status

A small, working routine tracker.
