# Spine Lab

An interactive, mobile-first spine-health assessment prototype — an X-ray-style
human body with a glowing vertebral column that re-poses (stand / sit / lift /
walk / sleep) across a guided, gamified assessment, with a mandatory educational
video gate and a Spine Score.

## Run it

It's a self-contained static site — no build step.

```bash
# any static server, e.g.
npx serve .
# or
python3 -m http.server 8000
```

Then open the served URL. (Opening `index.html` directly via `file://` won't work
because the runtime fetches the `.jsx`/asset files over HTTP.)

## Structure

```
index.html     entry — the design runtime + the embedded video-gate overlay
support.js      Claude Design runtime that renders the app
assets/         pose imagery (WebP): stand · sit · lift · walk · sleep · watch
```

## Notes

- Authored for a **390 × 844** phone viewport.
- Loads React, Babel and fonts from CDN, so it needs network on first load.
- The educational clip is a **mandatory gate**: the first screen is clean, and
  the clip must be watched before advancing past step 1. The ⓘ button (right
  edge) opens dismissable replay clips.
- Pose images are WebP-optimised (~50 KB each).

Spine Severity scoring follows Dr. Ayush Sharma's Spine Severity System (SSS).
