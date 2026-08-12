# Signlytic AI Desktop App

**Status:** Beta available for Windows. Mac app upcoming.
**Built with:** Electron

## Download

| Platform | Version | Download |
|----------|---------|----------|
| Windows 11 | v0.3.5 beta | **[Signlytic AI Setup 0.3.5.exe](https://github.com/Iyanuoluwa007/Signlytic-Overlay/releases/download/desktop-v0.3.5/Signlytic.AI.Setup.0.3.5.exe)** (99 MB) |
| macOS | upcoming | not yet available |

The installer is unsigned, so Windows SmartScreen will warn on first run.
Choose **More info**, then **Run anyway**.

## Overview

The desktop app brings BSL signing to your whole computer, not just your
browser. The Chrome extension only sees web pages; this reads what Windows
itself is hearing, so it works with video calls, media players and any other
desktop application.

It does that by reading **Windows 11 Live Captions**, which transcribes
system audio. Whatever your computer is playing, Live Captions transcribes
it and the app signs it.

## What works today

- Windows 11 Live Captions read live and signed as they are spoken
- 2D skeleton renderer (default) and 3D avatar renderer
- Manual text entry, so the app is usable without captions
- Sentences queue rather than cutting each other off mid-sign
- Words with no sign in the dictionary are fingerspelled rather than skipped

## Requirements

- Windows 11 22H2 or later, for Live Captions. The first time you open Live
  Captions, Windows asks you to accept terms and download a speech model.
  That is a one-off Windows step and cannot be done for you.
- An internet connection. Gloss translation and sign data are fetched from
  the Signlytic API.

## Known limitations

- In 3D mode the hands currently sit lower than they should. 2D is the
  default and is unaffected.
- No system tray or auto-start yet.
- Sign data is fetched rather than bundled, so the app needs a connection.

## macOS

The app itself runs on macOS through manual text entry. What is missing is
caption capture: macOS exposes captions through the Accessibility API rather
than the UI Automation interface used on Windows, which needs a separate
signed helper and explicit permission from the user. Everything after the
text arrives is already shared between both platforms.

## Feedback

[Leave feedback here](https://forms.gle/oTy7Bi414fuThFc1A)
