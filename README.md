# ⏱️ Stage Timer

A single-file, dependency-free countdown timer built for stage talks, exams, and any situation where a room full of people need a big, unmissable clock.

No build step, no npm install, no backend — it's one `index.html` you can open locally or drop on any static host.

## Features

- 🕐 **Setup screen** — pick minutes and seconds with tap or press-and-hold arrows
- 🖤 **High-contrast display** — pure black background, pure white digits, designed to stay legible when projected
- 🔴 **5-minute warning** — screen turns red and beeps 4 times when 5 minutes remain
- ⏰ **Time's up alert** — beeps 4 times again at zero, then switches to a red overtime counter
- ⏸️ **Pause / resume / restart** controls
- 🖥️ **Fullscreen mode** with auto-hiding controls (tap or move the mouse to bring them back; long-press to exit on touch)
- 🔗 **Shareable links** — generates a URL with the exact end time baked in, so anyone who opens it sees a live, synced countdown
- 📱 **Fully responsive** — no overflowing buttons or clipped text on mobile, in portrait or landscape
- 🔋 **Keeps the screen awake** while running, where the browser supports it
- 🚪 **Accidental-exit guard** — warns before closing the tab or hitting back mid-countdown

## Usage

1. Open `index.html` in any modern browser (desktop or mobile).
2. Set the minutes/seconds and hit **Start**.
3. Tap the fullscreen icon to go full-screen for projection.
4. Use **Share** to copy a link that opens the same countdown, synced, on another device.

No installation, no dependencies, no server required to run it locally.

## Hosting it online

This is a static file, so any static host works. For a free HTTPS URL with zero manual certificate setup:

- **GitHub Pages** — push this repo, then enable Pages in **Settings → Pages** (source: main branch)
- **Netlify** or **Vercel** — drag and drop `index.html` onto their dashboard
- **Cloudflare Pages** — connect the repo, deploy

> **Note on HTTP vs HTTPS:** the app works over plain HTTP, but two browser features — screen wake lock and the clipboard API — are restricted to secure (HTTPS) contexts. Serving over HTTPS is recommended so the "keep screen awake" and "copy share link" features work reliably. The share button always links using whatever protocol the page itself is served on.

## Browser support

Built with standard Web APIs:
- [Screen Wake Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Wake_Lock_API) (optional — degrades gracefully if unsupported)
- [Clipboard API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API) with a fallback for older/insecure contexts
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) for the alert beeps (no audio file needed)
- CSS container queries for responsive digit sizing

Works in current versions of Chrome, Edge, Firefox, and Safari.
