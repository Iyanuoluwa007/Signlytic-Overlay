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
| Chrome Extension | Chrome | v0.3.8 beta | [signlytic-extension.zip](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/v0.3.8/signlytic-extension.zip) |
| Desktop App | Windows 11 | v0.3.6 beta | [Signlytic AI Setup 0.3.6.exe](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/desktop-v0.3.6/Signlytic.AI.Setup.0.3.6.exe) |
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

**[Download Beta v0.3.8](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/v0.3.8/signlytic-extension.zip)** or see the [install page](https://signlytic-ai-website.vercel.app/extension).

See the [`Extension/`](./Extension) folder for source code and install instructions.

---

### Software App - Desktop App (Windows beta, Mac upcoming)

BSL signing for your whole computer, not just your browser. It reads Windows 11 Live Captions, which transcribes system audio, so it works with video calls, media players and any other desktop application.

**[Download for Windows](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/desktop-v0.3.6/Signlytic.AI.Setup.0.3.6.exe)** (v0.3.6 beta, 99 MB)

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

---

## Third-party assets and licensing

The code in this repository is the author's own work. It does **not** cover
third-party assets used while running or developing the project, which remain
under their own terms.

### 3D avatar models

The 3D avatar models are Mixamo characters and are **not licensed for
redistribution by this project**. They are used for rendering only, and are
not offered for download, resale, or redistribution as standalone assets.
Anyone building on this project should obtain their own models from Mixamo
under an Adobe account and accept Adobe's terms directly:
https://www.mixamo.com

If a model file appears in this repository, its releases, or its history,
that is unintentional and not an offer to distribute it. Please open an issue
and it will be removed.

### Other third-party material

The same applies to any other third-party asset that may be present without
having been excluded: sign language video or pose data derived from
third-party corpora, pretrained model weights, fonts, icons, and audio. Each
remains the property of its owner and is subject to that owner's licence.
Their presence here is incidental to development and is not a grant of any
right to redistribute them.

Nothing here is intended to distribute third-party assets. If you believe
something has been included that should not have been, please open an issue
and it will be taken down.
## Licence and attribution

Signlytic AI is released under the MIT Licence. See [LICENSE](LICENSE) for the
full text.

Copyright (c) 2025 Oke Iyanuoluwa Enoch.

You are free to use, modify and build on this work, commercially or otherwise.
The licence asks one thing in return, and it is not optional: **keep the
copyright notice and the licence text with any copy or substantial portion of
the software.** That notice is how the work stays credited to its author.

If you fork this project, publish something derived from it, or use it in a
product, paper or demo, please also credit it visibly and link back here:

> Built on [Signlytic AI](https://github.com/Iyanuoluwa007/Signlytic-Overlay)
> by Oke Iyanuoluwa Enoch.

Academic or written work can cite it as:

> Oke, I. E. (2025). *Signlytic AI: real-time English to British Sign Language
> translation*. https://github.com/Iyanuoluwa007/Signlytic-Overlay

The MIT Licence covers this project's own code. It does not extend to the
third-party assets described above, which stay under their owners' terms.
