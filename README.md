# BackSignal

**Your Personal Spine Severity Score** — a doctor-verified, video-led screening
for **lower-back (lumbar) pain only**, grounded in the **Spine Severity System
(SSS)** by **Dr Ayush Sharma** (Dept. of Spine Surgery).

Self-contained, hand-editable static site — no build step.

```bash
npm start          # → npx serve .
# or: python3 -m http.server 8000
```

Open the served URL (not `file://` — assets load over HTTP).

## Flow (video-led)

`Intro video → Connect health device → About you → 6 SSS steps → Daily habits → Score`

Each step pairs a short explainer video with exactly the data the SSS chart collects.

## The 6-step SSS score (0–11)

| Step | Input | Points |
|---|---|---|
| 1 · Back pain | VAS 0–10 (faces) | 0–3→0, 4–6→1, 7–10→2 |
| 2 · Sciatica | Leg pain / radiculopathy 0–3 | 0–3 |
| 3 · Disability | Modified ODI (5 activities × Normal/Mild/Severe = 0–10) | 0–2→0, 3–5→1, 6–10→2 |
| 4 · Body load | BMI (from height/weight) | <25→0, 25–29.9→1, ≥30→2 |
| 5 · Chronicity | Acute <3wk / Subacute 3–6wk / Chronic >6wk | 0 / 1 / 2 |
| 6 · Red flags | cancer, weight loss, fever, trauma, bladder/bowel, saddle, neuro | any → auto **11** |

**Bands:** 0–3 LOW · 4–6 MILD–MODERATE · 7–9 MODERATE–SEVERE · 10–11 SEVERE/HIGH RISK
→ education / physiotherapy / specialist / urgent care.

The **Daily Habit Snapshot** (sitting/walking/exercise/sleep) is **informational
only** — it does not change the clinical score (per the SSS chart). It can be
auto-filled from a connected health device and updates over time.

## Editing

- **Videos:** paste YouTube IDs into `APP.videos` at the top of `index.html`
  (intro + one per step). Empty `id` shows the script as a placeholder. Record
  vertical (9:16) clips — intro 30–45s, step clips ~15–25s.
- **Links:** `APP.links` (website / research / youtube).
- **Scoring & steps** live in `index.html` (`STEPS` array + scoring helpers),
  kept 1:1 with the SSS chart.

## Scope

- **Lower back / lumbar only** — no cervical/thoracic, no lifting tests (not in
  the source framework).
- Screening & decision-support tool — not a diagnosis or a substitute for
  clinical judgment.
