# Changelog

All notable changes to this project will be documented in this file.

## [2.7.5] - 2026-07-18

### Changed
- Added a configurable **Parameters** screen (saved in `data/settings.ini`) for token import scale and default folders (maps, videos, tokens, sessions), plus default grid type when enabling Grid.
- Added configurable **Token batch spacing** in **Parameters** to control spacing when importing multiple tokens.
- Updated Open/Locate file pickers so `.json` session files are explicitly visible in the primary filter lists.

### Documentation
- Added a 2.7.5 release highlights section to README and in-app help.
- Updated license version note to reference 2.7.5.


## [2.7.0] - 2026-07-16

### Added
- Video map playback support in the app workflow, including `.mp4`, `.webm`, `.mkv` and `.m4a` handling.
- Heavy video detection for likely problematic sources using file heuristics and stream metadata (codec/resolution when available).
- Informational warning when opening heavy videos to clarify potential playback limitations.
- Automatic lite playback profile for heavy videos:
	- reduced frame-processing frequency
	- stronger display downscale to protect UI responsiveness
- Cached 1080p transcode attempt for all detected heavy videos when `ffmpeg` is available.
- Token system on DM map: import token images, select, move, resize, rotate, delete with keyboard.
- Dedicated Token controls row under Open Map: Import Token and Token tool.
- Player token synchronization so token placement/manipulation on DM is reflected on Player view.
- Token handles with explicit action icons:
	- orange rotate handle
	- blue resize handle
- Fog toggle button near Reset Fog to enable/disable fog visibility on Player side.

### Improved
- Grid behavior:
	- default Type switches to Square when Grid is enabled from None
	- grid overlay works on both DM and Player with video sources
	- grid rendering optimized with cache in video paths
	- player map scale remains stable when toggling Grid on/off
- DM zoom navigation:
	- added horizontal (bottom) and vertical (right) scrollbars on DM view when zoomed in
	- scrollbar state is synchronized with wheel zoom and middle-mouse pan
	- scrollbars auto-hide when not needed or when DM is in video mode
- Video rendering architecture migrated to frame/sink compositing path for reliable overlay drawing.
- Performance when using video + grid + player by avoiding dual decoder paths and sharing DM frames with Player.
- Video playback resilience on high-load sources by selecting a safer render profile at runtime.
- VP9 4K streams now force lite render profile to avoid UI starvation and "Not responding" states.
- Token manipulation UX:
	- resize now preserves original image aspect ratio
	- orange rotate handle hit area significantly increased for easier grabbing
	- handle hit testing performed in screen-space pixels for consistent interaction at any zoom
- Fog/token interaction:
	- when Token tool is active, fog brush painting and brush preview are disabled on DM canvas
	- tokens remain hidden under fog on Player side
- Session load resilience:
	- missing map/media files are first searched in the session folder
	- if not found, user is prompted to locate the file
	- located replacements are remembered for future loads
	- resolved map path can be persisted back to the loaded session file

### Fixed
- Session persistence:
	- Save/Save As now reliably persists tokens in session JSON
	- Load Session restores tokens after map/mask setup without being reset by duplicate load logic
	- selecting a `.json` session file from Open Map now opens it as a session

### Documentation
- Updated in-app help and README with Token feature usage and behavior notes.
- Added documentation for DM zoom navigation scrollbars and session missing-file recovery behavior.
- Updated code comments/docstrings for video limitation handling and mitigation flow.
- Updated in-app help and README with explicit limitation notes and best practices.

### Packaging
- Rebuilt executable as Veilforge 2.7.0 with required media and PyMuPDF hidden imports.

## [2.6.0] - 2025-12-16

### Added
- In-app Help window with tabs: README, Credits, Use License
- Donation UI: Donate button + QR code (in Help and DM toolbar)
- Project version constant and window title version string
- Added save confirmation on exit and before opening a new map

### Improved
- Polished toolbar alignment (Player Screen + Donate)
- Better readability for QR hint text on dark themes

### Notes
- README intentionally contains no donation URL; donations are handled inside the app UI.
