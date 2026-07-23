# Veilforge — Fog of War (DM Tool)

Veilforge is a lightweight desktop tool for tabletop RPGs that lets a DM reveal a map progressively (“fog of war”), project it to a second screen for players, and add quick annotations on top.

> **Donate inside the app:** open **Help → README** to find the Donate panel (QR + button).

## User Interface

- Update interface version with an audacious **Tactical Studio** UI direction.


### Video playback limitations and stability notes

- Very heavy videos (notably **4K** and/or high bitrate files) can saturate decode/render resources on some PCs : heavy-video detection with user warning (size + 4K hints, and codec/resolution metadata when available).
- Automatic **lite render profile** (lower frame processing load + stronger display downscale).
- **VP9 4K** streams force lite profile automatically.
- For every detected heavy video, Veilforge attempts a local **1080p cached transcode** when `ffmpeg` is available.

Best practice:
- Prefer 1080p assets for long sessions, or prepare a lighter version of very large video maps.


## Tokens

Tokens are image markers placed on top of the map (creatures, NPCs, props, effects).

- Click **Import Token** to load one or multiple `.png` / `.jpg` token images.
- Imported tokens are auto-arranged around map center with spacing (not stacked).
- Token size is normalized on import for visibility, and can be adjusted with **Parameters > Token import scale**.
- Multi-import spacing can be adjusted with **Parameters > Token batch spacing**.
- Enable **Token tool** to manipulate tokens on the DM canvas:
  - Drag token body: move
  - Blue handle icon (top-right): resize
  - Orange handle icon (above token): rotate
- Right-click a selected token to open the context menu:
  - **Undo** / **Redo**
  - **Rotate** / **Resize**
  - **Copy** / **Paste** / **Delete**
- Keyboard shortcuts for tokens:
  - **Ctrl + Z**: undo token action
  - **Ctrl + Y**: redo token action
  - **Ctrl + C**: copy selected token
  - **Ctrl + V**: paste copied token
- **Delete** or **Backspace**: remove selected token


## Sessions (Save / Load)

Picker visibility note: In file search dialogs, `.json` session files are explicitly listed in the main filter so they are visible without switching filters.

## Parameters
- **Parameters** includes a configurable default folder for **Save/Load Session**.
- **Parameters** includes **Token batch spacing** for multi-token import placement.
- Dialog text uses a high-contrast style for better readability.

## Credits

**Cedric Dagobert** — AI co-developer (versions 2.7.x)
