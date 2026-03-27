# Rose[] — Rozpusta Game Library

A desktop library manager for your locally installed Ren'Py games. If you have dozens of games scattered across folders and no easy way to track them — this app is for you.

**[⬇️ Download latest version (Windows)](https://github.com/ipointg/rozpustaApp-releases/releases/latest)**

---

## What it does

Rose[] scans your games folder, automatically identifies each game, and pulls metadata from F95Zone — cover art, description, tags, version info, and release date. Everything is displayed in a clean interface so your collection finally looks like a proper library.

## Key features

- **Auto-identification** — point it at your folder and Rose[] finds and recognizes your games automatically
- **Version tracking** — see at a glance which games have updates available; UPD badge in the list, full notification on the detail page
- **Status badges** — Completed, Abandoned, On Hold shown directly on covers
- **Cover art & metadata** — banners, descriptions, genres, and release dates fetched and cached locally
- **Multiple folders** — manage several game directories at once, switch between them instantly
- **Search & filter** — search by title, sort A→Z, filter by status or updates, browse all folders at once or focus on one
- **Auto-updates** — the app updates itself silently; a button appears in the footer when a new version is ready
- **Community database** — powered by a shared game database that grows as users contribute new discoveries
- **Works offline** — metadata is cached locally after the first sync, no internet required to browse your library
- **Unrecognized games** — if a game can't be matched automatically, Rose[] asks you to confirm or paste a link manually, then contributes it to the shared database

## How it works

On first launch, choose your games folder. Rose[] scans it, matches games against the community database, and syncs missing metadata directly from F95Zone. After that, hit Sync any time to check for version updates. The app also refreshes data quietly in the background while it's open.

---

## Changelog

### [0.3.3] — 2026-03-27

**Added**
- **Auto-update** — the app now checks for new versions in the background; when an update is ready, a button appears in the footer — click "Restart to update" and you're done; no need to manually download new versions ever again

**Fixed**
- Games from sibling folders no longer leak into the Active Folder view
- Games with "Part 2" in the folder name are no longer incorrectly matched to the base game

---

### [0.3.2] — 2026-03-13

**Added**
- **UPD badge** in the game list — appears next to any game that has a newer version available; click it to open the F95Zone page directly in your browser
- **"Updates" filter** — new filter next to Completed / Abandoned / On Hold; shows only games with available updates
- **"New Version Available" label** on the game detail page — disappears automatically once you confirm you've updated
- **"Check on F95" button** — appears on the update notification alongside "I have updated"
- **Live DB sync** — the app quietly checks for new versions and status changes in the background

**Fixed**
- "New Version Available" label no longer disappears on its own a few seconds after opening the app
- Game list now reflects updates immediately after checking or confirming an update — no restart needed
- When two folders are confirmed as the same game, both now stay visible as separate installs

---

### [0.3.1] — 2026-03-11

**Added**
- Status labels on game banners — Completed, Abandoned, On Hold badges in the top-left corner
- Clear button in the search field
- "Check for updates" button on game detail page
- Status bar in the footer — shows current game count and app version

**Fixed**
- Games that are finished were sometimes shown as Abandoned — Completed always takes priority now
- "Update available" warning no longer appears for mismatches like `v1.0` vs `1.0`
- Syncing via F95Zone link now also saves status and release date correctly

**Changed**
- Game DB updated automatically 3 times a week — statuses and versions refreshed centrally

---

### [0.3.0] — 2026-03-08

**Added**
- Sidebar filter toolbar: search, sort (A→Z / Z→A / off), three view modes — active folder, all folders grouped, all games flat
- "Possible match found" confirmation card
- "Game not recognized" banner — prompts to paste an F95Zone link manually
- Filter mode saved and restored between restarts

**Fixed**
- Sync no longer assigns wrong game data — results validated against folder name
- Footer no longer takes up space when no sync is in progress
- Long names truncate with ellipsis

**Changed**
- Sidebar restructured; "Select a Folder" renamed to "Available Folders"

---

### [0.2.4] — 2026-03-08

**Added**
- F95Zone login integrated directly into the app UI
- Grouped sidebar with +/− collapse toggle
- Live game updates during sync
- Cancel sync button
- Progress bar animation

**Fixed**
- Wrong game matching for several games
- Banner quality: full-size image instead of thumbnail
- Deleted F95Zone threads handled gracefully

**Changed**
- Game detail layout redesigned Steam-style: full-width banner, glass content panel
