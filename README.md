<div align="center">

# ⚡ PPL Routine Tracker

**A mobile-first PWA for Push / Pull / Legs training with a Solo Leveling-inspired hunter stats system.**

Built for dumbbell-based training with an adjustable bench.

[![Version](https://img.shields.io/badge/version-1.4.2-4a9eff?style=flat-square&labelColor=03030e)](.)
[![PWA](https://img.shields.io/badge/PWA-ready-26c47a?style=flat-square&labelColor=03030e)](.)
[![Storage](https://img.shields.io/badge/storage-localStorage-7744ff?style=flat-square&labelColor=03030e)](.)

</div>

---

## 📁 Files

| File | Purpose |
|---|---|
| `index.html` | Workout tracker and session logger |
| `hunter-stats.html` | Hunter stats — XP, levels, anime body diagram |

Deploy both to the same folder. They share data through `localStorage` and link to each other.

---

## ✨ Features

### 🏋️ Workout Panels (Push / Pull / Legs / Abs)
- 50 exercises across all four days, grouped by muscle section
- Exercise cards show name, sets × reps, rest time, and colored muscle tags
- Tap any card to expand the full coaching description
- Static tips box on each panel with session-specific advice

**Section grouping:**
- **Push:** Chest → Shoulders → Triceps
- **Pull:** Back → Biceps → Forearms → Rear Delts
- **Legs:** Warmup (7 exercises) → Quads → Hamstrings → Glutes → Calves
- **Abs:** Core Stability → Flexion → Rotation & Anti-Rotation

### 📅 Session Logging
- **Log today** — multi-group days stack (Legs + Abs on the same day both register)
- **Log a previous day** — backfill any date from the Log tab
- **Rest day** tracking

### 📊 Log Tab
Streak counter · color-coded monthly calendar

---

## ⚡ Hunter Stats (`hunter-stats.html`)

| Attribute | Day | XP Source |
|---|---|---|
| Chest, Shoulders, Triceps | Push | 10 XP / session |
| Back, Biceps, Forearms | Pull | 10 XP / session |
| Quads, Hamstrings, Glutes, Calves | Legs | 10 XP / session |
| Core | Abs | 10 XP / session |

**Visual progression:** dark tint → color fill (Lv 5) → glow (Lv 10) → max glow (Lv 20)

**Rank system:** `E` → `D` → `C` → `B` → `A` → `S — Shadow Sovereign` (150 sessions)

**Tabs:** Stats (profile + anime body diagram) · Quests (daily/weekly/milestones) · Feats (14 achievements)

---

## 🚀 Setup

### GitHub Pages (recommended)
1. Upload both files to a GitHub repo
2. **Settings → Pages** → source: main branch root
3. Live at `https://yourusername.github.io/your-repo/`
4. Mobile: **Share → Add to Home Screen** to install as a PWA

### Local
Download both files to the same folder, open `index.html` in any browser.

---

## 💾 Data Storage

| Key | Contents |
|---|---|
| `ppl_v3` | Session log (dates + muscle groups) |

All data is local to your browser. Clearing browser storage resets everything.

> Routine customization localStorage keys (`ppl_routines_v1`, `ppl_sr_v1`, `ppl_ss_v1`) are no longer used and can be cleared safely.

---

## 📋 Patch Notes

### v1.4.2 — Lateral/Front Raise Superset Restored
- Lateral Raise and Front Raise on Push day re-grouped as a superset

### v1.4.1 — Exercise List Reverted to Previous Version
- Push: removed Arnold Press; Lateral Raise and Front Raise restored to individual cards (no superset)
- Pull: removed Chest-Supported DB Row
- Legs: removed Nordic Curl (replaced by DB Lying Leg Curl, already present) and DB Walking Lunge
- Abs: removed Dead Bug, DB Ab Rollout, and Lying Leg Raise — back to 6 exercises (Plank, Weighted Crunch, Reverse Crunch, Bicycle Crunch, DB Russian Twist, Side Plank)

### v1.4.0 — Simplified to Static Exercises
- Removed the entire inline routine editor (edit sheet, exercise bank, EXERCISE_BANK data, routines/SR/SS localStorage)
- Exercises are now rendered as static HTML — no JavaScript required to display them
- Removed live Routine Review; restored the original static tips box on each panel
- Routine changes going forward will be made directly to the source file

### v1.3.4 — Larger Small Text
- Section titles, muscle tags, descriptions, rest labels, and review text all bumped up for readability

### v1.3.3 — Legs Warmup as Individual Exercises
- Single "Dynamic Warmup" card replaced with 7 individual exercises under their own Warmup section

### v1.3.2 — UI Cleanup
- Removed redundant Primary/Secondary muscle text from inside exercise cards
- Muscle Volume chart and History removed from Log tab

### v1.3.1 — Section Grouping + Superset Restrictions
- Exercises grouped by muscle section within each panel
- Reorder and superset restricted within sections only

### v1.3.0 — Inline Routine Editor + Superset System + Live Review
- Pencil icon on each panel opens a two-column edit sheet — no separate tab required
- Add, remove, reorder exercises and edit sets/reps/rest inline
- **⚡ Superset toggle** — mark consecutive exercises to render as a superset pair on the panel
- **Live Routine Review** — replaces static tips with sequencing, overlap, and superset analysis updated in real time
- Sequencing warnings (compounds before isolations), volume check, muscle overlap warnings (same primary hit 3+ times), superset quality feedback
- All changes persist independently in separate localStorage keys (`ppl_routines_v1`, `ppl_sr_v1`, `ppl_ss_v1`)
- Edit sheet matches main panel aesthetic (dark cards, colored muscle tags, day-accent border)
- Orphaned Build tab UI fully removed

### v1.2.0 — Previous Day Logging
- Log a Previous Day widget added to the Log tab
- Date picker defaults to today; merges with existing entries for the same date

### v1.1.2 — Desktop Fix + Body Visibility
- Desktop scrolling fixed — natural page scroll at 768px+
- Hunter Stats body visible at low levels (tint applied from level 0)
- Abs grid lines visible from the start

### v1.1.1 — Anime Body Diagram
- V-taper anatomy, segmented abs, diamond calves
- Solo Leveling aesthetic: navy background, blue ambient glow, scan-line animation
- Eye glow scales with total sessions

### v1.1.0 — Hunter Stats Launch
- XP system with quadratic leveling, rank E → S (Shadow Sovereign at 150 sessions)
- 11 muscle attributes with SVG body diagram; visual progression from dark tint → color fill → glow → max glow
- Quests tab (daily/weekly/milestones) and Feats tab (14 achievements)
- Multi-type logging, color-coded calendar, desktop sidebar

### v1.0.0 — Initial Release
- Push / Pull / Legs / Abs panels with 50 exercises
- Day logging, streak counter, calendar, daily motivational quote
- Mobile PWA via Add to Home Screen
