# Signlytic Overlay - Chrome Extension

**Version:** 0.4.1 (Beta)
**Browser:** Chrome (Chromium-based browsers)
**Install:** Manual (Load Unpacked)

---

## Download

**[Download Beta v0.4.1](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/v0.4.1/signlytic-extension.zip)**
or visit the [extension page](https://signlytic-ai-website.vercel.app/extension)
for install instructions.

Signing on the whole desktop rather than just browser tabs is the
[desktop app](../Software%20App), which is now on Windows and macOS.

---

## Install in 3 Steps

1. **Download and unzip** the folder from the link above
2. Open **chrome://extensions** and enable **Developer Mode** (toggle top-right)
3. Click **Load Unpacked** and select the unzipped `signlytic-extension` folder

The Signlytic icon will appear in your Chrome toolbar.

---

## How to Use

### Auto-detect mode (default)
Navigate to any video with captions enabled (YouTube, BBC iPlayer, Netflix etc). The overlay panel appears automatically in the bottom-right corner. Enable captions on the video and signing begins.

### Microphone mode
Select **Microphone** in the popup. Speak in English, and the overlay translates your speech to BSL signing in real time.

### Manual mode
Select **Manual** in the popup. A text input bar appears at the bottom of the panel. Type any English sentence and press **Sign** or **Enter**.

---

## Features

- Auto-detect captions on YouTube, BBC iPlayer, Netflix, Amazon Prime, All4, Disney+
- Web Speech API microphone fallback (en-GB)
- Manual text input
- 2D skeleton animation (MediaPipe pose landmarks)
- 3D Mixamo avatar (Male / Female)
- 192 BSL signs bundled for offline use
- Draggable panel: drag the header to reposition
- Resizable panel: drag bottom-right corner
- Position snap: Top L / Top R / Bot L / Bot R in popup settings
- Sign speed control (0.5x to 2.0x)

---

## Source Structure

```
signlytic-extension/
  manifest.json          MV3 manifest
  background.js          Service worker: message hub, auto-inject
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
  data/signs/core/       192 bundled BSL sign pose JSONs
  icons/                 icon16/48/128.png
```

---

## Known Limitations (Beta)

- Chrome only (Chromium-based browsers should work)
- Manual install required, not yet on Chrome Web Store
- 3D avatar requires internet connection to load a GLB file on first use (3.5 MB male, 5.4 MB female, cached after)
- Signs not in the 192 bundled set will fingerspell unless the local Signlytic AI dashboard is running
- Mic mode requires microphone permission in Chrome

---

## Attribution

Pose landmarks extracted from BSL SignBank dictionary videos for research and accessibility purposes.
