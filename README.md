<div align="center">

<br>

# *V*OID

**A cinematic HLS stream player that lives in a single HTML file.**

<br>

<img src="https://img.shields.io/badge/zero-dependencies-1a1a2e?style=flat-square&labelColor=0a0a0f" alt="zero deps" />
<img src="https://img.shields.io/badge/single-file-1a1a2e?style=flat-square&labelColor=0a0a0f" alt="single file" />
<img src="https://img.shields.io/badge/HLS-ready-c4a882?style=flat-square&labelColor=0a0a0f" alt="HLS" />

<br>

**[Live Demo](https://volveezz.github.io/void-player/)**

<br>

</div>

---

## What is this

A premium video player for `.m3u8` HLS streams. No build step, no framework, no npm install. Open `index.html` in a browser. Paste a URL. Watch.

Built around the idea that the video floats in a void — ambient light bleeds from the video content into the surrounding space, like a display in a dark room.

## Usage

```
# literally just
open index.html

# or serve it
python -m http.server 8000
npx serve .
```

Paste any `.m3u8` URL into the input bar and press **Enter** or click **Load**.

## Features

| | |
|:--|:--|
| **Ambient backlight** | Samples dominant color from video frames, drives 3 blurred orbs behind the player in real-time |
| **Film grain** | SVG noise texture at 3.5% opacity across the viewport |
| **Custom controls** | Auto-hide after 3s, spring-eased slide-up, cursor disappears |
| **Progress bar** | Hover-expand, scrub head with glow, time tooltip, buffer visualization |
| **Play/pause pulse** | Glassmorphic circle animates outward from center |
| **Volume OSD** | Top-right heads-up display on keyboard volume change |
| **Speed selector** | Popup menu + `<` / `>` keyboard cycling |
| **Picture-in-Picture** | `P` key, floating pill indicator when active |
| **Fullscreen** | `F` key or double-click the video |
| **Keyboard shortcuts** | `?` to see all 14 bindings |

## Keyboard

```
Space ···· Play / Pause          F ········ Fullscreen
M ········ Mute toggle           P ········ Picture-in-Picture
← ········ Skip -10s             → ········ Skip +10s
J ········ Skip -5s              L ········ Skip +5s
↑ ········ Volume up             ↓ ········ Volume down
< ········ Speed down            > ········ Speed up
0-9 ······ Seek to 0–90%         ? ········ Show shortcuts
```

## Design

Three typefaces: **Instrument Serif** (italic branding), **Geist Mono** (data/telemetry), **Space Grotesk** (UI elements). Warm accent `#c4a882` against near-black `#050507`. Glassmorphic overlays with `backdrop-filter: blur`. All transitions use `cubic-bezier(0.16, 1, 0.3, 1)`.

## Tech

- [hls.js](https://github.com/video-dev/hls.js) from CDN for HLS decoding
- Canvas 2D for video color sampling (8x8 downscale, ~2fps)
- Zero build tools, zero node_modules, zero config
- Falls back to native HLS on Safari

## License

MIT
