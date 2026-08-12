# Signlytic Overlay

**Real-time British Sign Language signing for Chrome and Windows.**

Signlytic Overlay detects live captions from YouTube, BBC iPlayer, Netflix and more - and translates them into animated BSL signing in a floating panel. Type or speak in English and watch the signs play back in real time.

[![Website](https://img.shields.io/badge/Website-signlytic--ai--website.vercel.app-0e7c6b?style=flat-square)](https://signlytic-ai-website.vercel.app)
[![Extension](https://img.shields.io/badge/Chrome_Extension-Beta-5eead4?style=flat-square)](https://signlytic-ai-website.vercel.app/extension)
[![Feedback](https://img.shields.io/badge/Feedback-Google_Form-white?style=flat-square)](https://forms.gle/oTy7Bi414fuThFc1A)

---

## Downloads

| Product | Platform | Version | Download |
|---------|----------|---------|----------|
| Chrome Extension | Chrome | v0.3.6 beta | [signlytic-extension.zip](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/v0.3.6/signlytic-extension.zip) |
| Desktop App | Windows 11 | v0.3.1 beta | [Signlytic AI Setup 0.3.1.exe](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/desktop-v0.3.1/Signlytic.AI.Setup.0.3.1.exe) |
| Desktop App | macOS | upcoming | not yet available |

Both are free and need no account. They are unsigned builds, so Windows SmartScreen warns on first run: choose **More info**, then **Run anyway**.

---

## What It Does

- Detects page captions automatically on YouTube, BBC iPlayer, Netflix, Amazon Prime, All4, Disney+ and more
- Falls back to microphone (Web Speech API) when captions are unavailable
- Translates English to BSL glosses using a rule-based converter with 11,000+ gloss vocabulary
- Animates signing using 2D skeleton (MediaPipe pose landmarks) or 3D Mixamo avatar (Three.js)
- 174 BSL signs bundled for offline use - extended to 5,203 signs when connected to the local Signlytic AI system
- Draggable, resizable, always-on-top floating panel

---

## Products

### Extension - Chrome Extension (Beta)

Real-time BSL signing overlay for Chrome. Works on any website with captions.

**[Download Beta v0.3.6](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/v0.3.6/signlytic-extension.zip)** or see the [install page](https://signlytic-ai-website.vercel.app/extension).

See the [`Extension/`](./Extension) folder for source code and install instructions.

---

### Software App - Desktop App (Windows beta, Mac upcoming)

BSL signing for your whole computer, not just your browser. It reads Windows 11 Live Captions, which transcribes system audio, so it works with video calls, media players and any other desktop application.

**[Download for Windows](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/desktop-v0.3.1/Signlytic.AI.Setup.0.3.1.exe)** (v0.3.1 beta, 99 MB)

The Mac app is upcoming: macOS exposes captions through a different system interface, which needs a separate signed helper. See the [`Software App/`](./Software%20App) folder for details and current limitations.

---

## Technology Stack

| Component | Technology |
|-----------|------------|
| Caption Detection | MutationObserver, Web Speech API |
| Gloss Conversion | Rule-based English → BSL (JS) |
| 2D Signing | MediaPipe Holistic pose landmarks + Canvas |
| 3D Signing | Three.js r128, Mixamo GLB avatars |
| Extension | Chrome MV3, iframe overlay architecture |
| Desktop App | Electron (planned) |
| Backend Integration | FastAPI (local), Groq Llama 3.3 70B |

---

## Related

This project is part of the broader **Signlytic AI** system - a bidirectional BSL translation pipeline featuring Video-SWIN-T sign recognition (100% Top-1 on 5,203 signs), Whisper speech recognition, Groq LLM translation, and Coqui XTTS v2 voice synthesis.

- **Website:** https://signlytic-ai-website.vercel.app
- **Live Demo:** https://signlytic-ai-website.vercel.app/demo
- **Feedback:** https://forms.gle/oTy7Bi414fuThFc1A

---

## Author

**Oke Iyanuoluwa Enoch**
Independent Robotics & AI Systems Engineer
[LinkedIn](https://www.linkedin.com/in/iyanuoluwa-enoch-oke/) · [GitHub](https://github.com/Iyanuoluwa007)
