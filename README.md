# Spine Lab

An interactive, mobile-first spine-health assessment prototype — an X-ray-style
human body with a glowing vertebral column that re-poses (stand / sit / lift /
walk / sleep) across a guided, gamified assessment, with a mandatory educational
video gate and a Spine Score.

## Run it

It's a self-contained static site — no build step.

```bash
npm start          # → npx serve .
# or any static server: python3 -m http.server 8000
```

Then open the served URL. (Opening `index.html` directly via `file://` won't work
because the runtime fetches its assets over HTTP.)

## Structure

```
index.html     entry — the design runtime + the embedded video-gate overlay
support.js      Claude Design runtime that renders the app
assets/         pose imagery (WebP): stand · sit · lift · walk · sleep · watch
```

## Notes

- Authored for a **390 × 844** phone viewport; no mock status bar (uses the device's own).
- Self-contained runtime (`support.js`); only fonts load from CDN.
- Pose imagery is WebP, 780 px (2×), ~40 KB each.
- The educational clip is a **mandatory gate**: the first screen is clean, and
  the clip must be watched before advancing past step 1. The ⓘ button (right
  edge) opens dismissable replay clips.

Spine Severity scoring follows Dr. Ayush Sharma's Spine Severity System (SSS).
