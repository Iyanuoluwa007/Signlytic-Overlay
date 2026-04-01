# Signlytic Overlay — Chrome Extension

**Version:** 0.3.5 (Beta)
**Browser:** Chrome (Chromium-based browsers)
**Install:** Manual (Load Unpacked)

---

## Download

**[Download Beta](https://signlytic-ai-website.vercel.app/extension)**

Visit the extension page for the latest version and install instructions.

---

## Install in 3 Steps

1. **Download and unzip** the folder from the link above
2. Open **chrome://extensions** — enable **Developer Mode** (toggle top-right)
3. Click **Load Unpacked** and select the unzipped `signlytic-extension` folder

The Signlytic icon will appear in your Chrome toolbar.

---

## How to Use

### Auto-detect mode (default)
Navigate to any video with captions enabled (YouTube, BBC iPlayer, Netflix etc). The overlay panel appears automatically in the bottom-right corner. Enable captions on the video and signing begins.

### Microphone mode
Select **Microphone** in the popup. Speak in English — the overlay translates your speech to BSL signing in real time.

### Manual mode
Select **Manual** in the popup. A text input bar appears at the bottom of the panel. Type any English sentence and press **Sign** or **Enter**.

---

## Features

- Auto-detect captions on YouTube, BBC iPlayer, Netflix, Amazon Prime, All4, Disney+
- Web Speech API microphone fallback (en-GB)
- Manual text input
- 2D skeleton animation (MediaPipe pose landmarks)
- 3D Mixamo avatar (Male / Female)
- 174 BSL signs bundled for offline use
- Draggable panel — drag the header to reposition
- Resizable panel — drag bottom-right corner
- Position snap — Top L / Top R / Bot L / Bot R in popup settings
- Sign speed control (0.5x — 2.0x)

---

## Source Structure

```
signlytic-extension/
  manifest.json          MV3 manifest
  background.js          Service worker — message hub, auto-inject
  content_script.js      Caption detection, mic, iframe positioning
  gloss/converter.js     English to BSL gloss rules (ES module)
  overlay/
    overlay.html         Panel UI
    overlay.js           2D renderer, sign queue, fingerspell fallback
    avatar3d.js          Three.js GLB bone driver
    three.min.js         Bundled Three.js r128
    GLTFLoader.js        Bundled GLTFLoader
  popup/
    popup.html           Settings popup
    popup.js             Settings logic
  data/signs/core/       174 bundled BSL sign pose JSONs
  icons/                 icon16/48/128.png
```

---

## Known Limitations (Beta)

- Chrome only (Chromium-based browsers should work)
- Manual install required — not yet on Chrome Web Store
- 3D avatar requires internet connection to load GLB files on first use (~55MB, cached after)
- Signs not in the 174 bundled set will fingerspell unless the local Signlytic AI dashboard is running
- Mic mode requires microphone permission in Chrome

---

## Attribution

Pose landmarks extracted from BSL SignBank dictionary videos for research and accessibility purposes.
