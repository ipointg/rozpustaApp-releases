# Rose[] — Rozpusta Game Library

A desktop library manager for your locally installed Ren'Py games. If you have dozens of games scattered across folders and no easy way to track them — this app is for you.

**[⬇️ Download latest version (Windows)](https://github.com/ipointg/rozpustaApp-releases/releases/latest)**

---

# Changelog

This file documents all significant changes to the **Rozpusta Game Library** app.

Versioning follows the [Semantic Versioning](https://semver.org/).


## [0.3.3] - 2026-03-27

### Added
- **Auto-update** — the app now checks for new versions in the background; when an update is ready, a button appears in the footer — click "Restart to update" and you're done; no need to manually download new versions ever again

### Fixed
- Games from sibling folders no longer leak into the Active Folder view (e.g. if two folders had the same name length, one would incorrectly show the other's games)
- Games with "Part 2" in the folder name (e.g. *A Wife And Mother Part 2*) are no longer incorrectly matched to the base game


---

## [0.3.2] - 2026-03-13

### Added
- **UPD badge** in the game list — appears next to any game that has a newer version available; click it to open the game's F95Zone page directly in your browser
- **"Updates" filter** — new filter next to Completed / Abandoned / On Hold; shows only games with available updates
- **"New Version Available" label** on the game detail page — replaces the old "New!" label; disappears automatically once you confirm you've updated
- **"Check on F95" button** — opens the game's F95Zone page in your browser; appears on the update notification alongside "I have updated"
- **Live DB sync** — the app now quietly checks for new versions and status changes in the background; your library stays up to date even if you leave the app open all day

### Fixed
- "New Version Available" label and update notification no longer disappear on their own a few seconds after opening the app
- Game list now reflects updates immediately after checking or confirming an update — no restart needed
- When two folders are confirmed as the same game, both now stay visible in the list as separate installs with their own version info


---

## [0.3.1] - 2026-03-11

### Added
- Status labels on game banners — Completed, Abandoned, On Hold badges appear in the top-left corner so you can see at a glance what's happening with a game
- Clear button in the search field — small × inside the input, clears search in one click
- "Check for updates" button on game detail page — fetches the latest version, release date and status directly from F95Zone for that game; disabled if the game has no F95Zone link
- Status bar in the footer — shows the current game count and app version; count reflects the active folder or current view mode

### Fixed
- Games that are actually finished were sometimes shown as Abandoned — now Completed always takes priority over any other status
- "Update available" warning no longer appears for version mismatches like `v1.0` vs `1.0` — these are treated as the same version
- Syncing a game via its F95Zone link now also saves its status and release date correctly
- Tooltips on social and window control buttons now use the same custom style as the rest of the UI instead of the native browser tooltip

### Changed
- Game DB is now updated automatically 3 times a week (Monday, Wednesday, Friday) — statuses and versions are refreshed centrally so your app always shows up-to-date info without having to individually check each game


---

## [0.3.0] - 2026-03-08

### Added
- Sidebar filter toolbar: search by game title, alphabetical sort (A→Z / Z→A / off), and three view modes — active folder, all known folders grouped, all games flat
- "All folders" mode: active folder pinned to top and highlighted; all known subfolders shown as separate groups
- "Possible match found" confirmation card — when a game is found in a search, the user is asked to confirm before the data is saved and contributed to the community DB
- "Game not recognized" banner for games that couldn't be matched — prompts to paste an F95Zone link manually
- Filter mode (active/all/flat) is now saved and restored between app restarts

### Fixed
- Sync no longer randomly assigns wrong game data — search results are now validated against the folder name before being applied
- Games with no reliable match are shown as "unrecognized" and never auto-matched to an unrelated game
- Community DB push now goes directly to `main` for the repo owner; regular users get a PR only when they discover genuinely new games
- Footer no longer takes up space when no sync is in progress
- Long folder and game names now truncate with ellipsis instead of clipping

### Changed
- Sidebar layout restructured: search and sort on the first row, view mode buttons on the second row
- Tooltips on filter buttons now match the header tooltip style
- Folder picker shows a folder icon placeholder when no banners have been loaded yet
- "Select a Folder" heading renamed to "Available Folders"


---

## [0.2.4] - 2026-03-08

### Added
- F95Zone login integrated directly into the app UI — no manual script needed
- Login status indicator: header button turns green when logged in
- Warning banner when sync is attempted without F95Zone authentication
- Grouped sidebar: games are now grouped under folder headers with +/− collapse toggle
- Subfolder cards shown on the folder picker screen alongside known folders
- Clicking a folder header in the sidebar switches to that subfolder
- Progress bar animation: shimmer and pulse effects during sync
- Live game updates during sync — banner, tags and description appear per-game without waiting for full sync to finish
- Cancel sync button — stops sync gracefully, saves progress already made
- Patreon and F95Zone links now open in the system browser
- Parent folder now inherits game data from subfolder caches (no more unknown stubs)
- `push-master-db-direct.js` script for pushing master DB directly to main branch
- GitHub CLI (`gh`) installed and configured

### Fixed
- Wrong game matching for FamilyChemistry-1.0-pc, AGirlOnATrain-1.0-pc, Kidnap-1.0-pc
- DuckDuckGo search landing on review/discussion tabs instead of main thread
- Banner quality: now fetches full-size lightbox image instead of thumbnail
- Sync order bug: master file now downloaded before reading local DB
- Master DB URL corrected to `ipointg/rozpusta_DB`
- 9 knownTitle collisions in master DB resolved
- Deleted F95Zone threads handled gracefully (keeps existing game data)
- Sync now only processes root-level games, not games in subfolders
- "Clear Cache" now removes all cache files, master DB and banners

### Changed
- Game detail layout redesigned Steam-style: full-width banner with vignette, glass content panel overlapping banner
- Tags moved to content area, restyled as pill-shaped with transparent background
- Buttons more rounded with hover glow effect
- Input fields styled to match app theme
- Sidebar has slightly different background for visual separation
- Fade-in animation when switching between games
- "Sync Folder" button disabled and shows "Syncing..." during active sync


---

## [0.2.3] - 2025-07-02
### Added
- Local Folders after scan and add are displayed and available for switching between them

### Fixed
- Freeze at the start of the application
- Master-file update mechanism fixed for Git branch

### Changed
- Banner pictures display priority changed to offline first


---

## [0.2.2] - 2025-06-22
### Changed
- Logic of updating local master-file and cache-file
- Updating release date improved
- Interfaces added for local and master game objects
- Refactored code, helpers functions separated
- Cursor updated for games list in UI


---

## [0.2.1] - 2025-06-19


---

## [0.2.0] - 2025-06-19
### Added
- Automatic fork and Pull Request to GitHub using token
- Display of `releaseDate` and notification when a newer game version is available
- New `knownTitles` field to improve game recognition

### Changed
- All paths for cache, banners, and `local-game-db.json` unified under:
  - `C:\Users\USERNAME\AppData\Roaming\erogame-library\rozpustaApp`


---

## [0.1.1] - 2025-06-18
### Fixed
- Bug where `bannerUrl` wasn’t updated when a game was added manually
- Improper merging of `knownTitles` between local and global files
- Introduced validation of `f95Url` as the unique key for each game


---

## [0.1.0] - 2025-06-17
### Added
- Initial MVP of the application
- Folder scanning for locally installed Ren'Py games
- Game detection via `options.rpy`, `screens.rpy`, `.exe`, and `README.txt`
- Local library with game launcher and display
- Support for local game cache via `local-game-db.json`
- Automatic saving of banners and metadata from F95Zone
- Visual indicators for update relevance: <7 days, <14 days, <30 days
- Manual input field for F95Zone game URLs in case update is needed
- Download of `master.json` from GitHub Pages
- Automatic Pull Request to repository with updated `local-game-db.json`