# Veilforge — Fog of War (DM Tool)

Veilforge is a lightweight desktop tool for tabletop RPGs that lets a DM reveal a map progressively (“fog of war”), project it to a second screen for players, and add quick annotations on top.

> **Donate inside the app:** open **Help → README** to find the Donate panel (QR + button).

[![Youtube Video](https://github.com/user-attachments/assets/4ebbe18a-2930-40af-b22f-c4077cb5ab57)](https://youtu.be/o7xHNwLNQTg)


## Features of v2.7.0

- **Video/audio support**: open `.mp4`, `.webm`, `.mkv`, `.m4a` files for playback on the DM canvas and player screen
- **Tokens**: import token images, then move/resize/rotate them on the DM map


## Video / Audio maps

- You can now open video or audio files directly as the map source.
- Supported formats include **MP4**, **WEBM**, **MKV**, and **M4A**.
- When a video file is loaded, playback starts automatically and loops on the DM canvas and player screen.

### Video playback limitations and stability notes

- Very heavy videos (notably **4K** and/or high bitrate files) can saturate decode/render resources on some PCs.
- In these cases, Windows can temporarily mark the app as **"Not responding"**.

Built-in mitigations:
- Heavy-video detection with user warning (size + 4K hints, and codec/resolution metadata when available).
- Automatic **lite render profile** (lower frame processing load + stronger display downscale).
- **VP9 4K** streams force lite profile automatically.
- For every detected heavy video, Veilforge attempts a local **1080p cached transcode** when `ffmpeg` is available.

Best practice:
- Prefer 1080p assets for long sessions, or prepare a lighter version of very large video maps.


## DM zoom navigation (Master screen)

- When zoom level is above 100% and movement is possible, Veilforge shows:
  - a **horizontal scrollbar** at the bottom
  - a **vertical scrollbar** on the right
Those bars let the DM move quickly through the zoomed map area.


## Tokens

Tokens are image markers placed on top of the map (creatures, NPCs, props, effects).
- Click **Import Token** to load a `.png` / `.jpg` token image.
- New tokens are placed near the center of the current map.
- Enable **Token tool** to manipulate tokens on the DM canvas:
  - Drag token body: move
  - Blue handle icon (top-right): resize
  - Orange handle icon (above token): rotate
- Right-click a selected token to open the context menu:
  - **Rotate** / **Resize**
  - **Copy** / **Paste** / **Delete**
  - **Duplicate** / **Bring to Front** / **Send to Back**
- Keyboard shortcuts for tokens:
  - **Ctrl + C**: copy selected token
  - **Ctrl + V**: paste copied token
- Press **Delete** or **Backspace** to remove the selected token.
- Tokens are synchronized to the **Player** window.
- On the Player side, tokens stay hidden under fogged areas (fog is drawn above tokens).

Important behavior:
- When **Token tool** is ON, the DM fog brush is intentionally disabled (including brush preview) to prevent accidental fog edits.


## Credits

**Cedric Dagobert** — AI co-dev (v2.7.0)
