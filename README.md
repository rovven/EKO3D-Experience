# EKO3D Scanner
https://rovven.github.io/EKO3D-Experience/
A web app that uses your phone camera to detect the **EKO mascot** and launch an AR experience , no app install required.

---

## How It Works

1. Open the app link on your phone browser
2. Tap **Open Camera** and allow camera access
3. Point your camera at the **EKO mascot image**
4. The app detects the mascot and automatically redirects you to the WebAR experience

---

## Features

- **Mascot detection** — Recognises the EKO mascot by its distinctive color signature (teal eyes, purple jacket, dark face screen) using real-time camera analysis
- **Auto-redirect** — 7-second countdown fallback so users always reach the AR experience even if scanning fails
- **QR-driven URL** — The destination URL is decoded automatically from `QrCode.png` at startup — no hardcoded links
- **No install needed** — Runs entirely in the browser, works on iOS Safari and Android Chrome
- **Camera permission flow** — Clean permission prompt before any camera access is requested
- **PWA support** — Can be added to home screen for a native app feel
- **Offline-capable** — Service worker caches assets so the app loads without internet after first visit
- **Confidence indicator** — Live progress bar shows how strongly the mascot is being detected
- **Haptic feedback** — Vibrates on successful detection (Android)
- **Dual detection** — Uses MindAR image tracking (precise) with automatic fallback to color-signature detection if no `.mind` target file is present

---

## Files

| File | Purpose |
|---|---|
| `index.html` | Main scanner app (all logic self-contained) |
| `Mascot.png` | Reference image used for fallback color detection |
| `QrCode.png` | QR code image — decoded at runtime to get the WebAR URL |
| `manifest.json` | PWA manifest (name, icons, theme) |
| `sw.js` | Service worker for offline caching |

---

## Hosting

Deployed via **GitHub Pages** — any HTTPS host works.  
Camera access requires HTTPS (GitHub Pages, Netlify, Vercel, etc.).

---

## Tech Stack

- [MindAR](https://hiukim.github.io/mind-ar-js-doc/) — image target tracking
- [jsQR](https://github.com/cozmo/jsQR) — QR code decoding
- Vanilla JS / HTML / CSS — no framework, no build step


