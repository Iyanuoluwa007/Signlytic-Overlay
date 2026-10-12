# Signlytic AI Desktop App

**Status:** Beta. Windows on 0.3.10, macOS on 0.3.9.
**Built with:** Electron

## Download

| Platform | Version | Download |
|----------|---------|----------|
| Windows 11 | v0.3.10 beta | **[Signlytic AI Setup 0.3.10.exe](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/desktop-v0.3.10/Signlytic.AI.Setup.0.3.10.exe)** (99 MB) |
| macOS 13 or later | v0.3.9 beta | **[Signlytic AI-0.3.9-universal.dmg](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/desktop-v0.3.9/Signlytic.AI-0.3.9-universal.dmg)** (208 MB, universal) |

Neither build is code-signed, so each needs talking past the operating system
once. Windows SmartScreen warns on first run: choose **More info**, then
**Run anyway**. macOS is stricter. Drag the app to Applications; the first
time, macOS will refuse to open it. Choose **Done**, then open **System
Settings**, **Privacy and Security**, scroll down to **Security**, choose **Open
Anyway** next to the message about Signlytic AI, and authenticate. On macOS 13
or 14 you can instead right-click the app and choose Open; on macOS 15 and later
that no longer works.

The Mac build is universal, so one file covers Apple silicon and Intel.

## Overview

The desktop app brings BSL signing to your whole computer, not just your
browser. The Chrome extension only sees web pages; this hears what the
computer itself is playing, so it works with video calls, media players and
any other desktop application.

How it gets the words differs by platform. On Windows it reads
**Live Captions**, the built-in feature that transcribes system audio. macOS
has no equivalent window to read, so the app recognises speech itself, from
the microphone or from system audio. Both produce the same thing, a caption
buffer revised in place, and everything after that point is shared.

## What works today

- Windows 11 Live Captions read live and signed as they are spoken
- macOS speech recognition, from the microphone or from system audio
- 2D skeleton renderer (default) and 3D avatar renderer
- Manual text entry, so the app is usable without captions
- Sentences queue rather than cutting each other off mid-sign
- Words with no sign in the dictionary are fingerspelled rather than skipped

## Requirements

- **Windows:** 11 22H2 or later, for Live Captions. The first time you open
  Live Captions, Windows asks you to accept terms and download a speech model.
  That is a one-off Windows step and cannot be done for you.
- **macOS:** 13 or later. The first time you start captions the app asks for
  microphone and speech recognition permission, and for screen recording if
  you pick system audio, which is how macOS gates capturing what other apps
  play.
- An internet connection. Gloss translation and sign data are fetched from
  the Signlytic API.

## Known limitations

- In 3D mode the hands currently sit lower than they should. 2D is the
  default and is unaffected.
- Neither build is code-signed or, on macOS, notarised.
- No system tray or auto-start yet.
- Sign data is fetched rather than bundled, so the app needs a connection.

## macOS

Caption capture now works, through speech recognition rather than by reading
system captions. Choose the microphone or system audio under **Listen to**.

This build is on its first release and is less tested than the Windows one.
Reading the macOS Live Captions window, which would be the closer analogue to
what Windows does, is written but unverified: it was proven able to read that
window with a standalone probe, but was never seen delivering a sentence end
to end inside the packaged app, because the Accessibility permission it needs
was never granted before that work stopped. It is kept on the
`macos-live-captions-unverified` branch of the main repository rather than
presented as finished.

## Feedback

[Leave feedback here](https://forms.gle/oTy7Bi414fuThFc1A)
