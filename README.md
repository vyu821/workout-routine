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
- Exercises unchanged: 57 total across Push, Pull, Legs, Abs with all section groupings and supersets preserved
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
- Reorder and superset restricted within sections

### v1.3.0 — Inline Routine Editor
- Two-column edit sheet, superset toggle, live routine review

### v1.2.0 — Previous Day Logging
- Backfill any past date from the Log tab

### v1.1.x — Hunter Stats + Desktop
- XP system, rank E→S, anime body diagram, desktop sidebar, multi-type logging

### v1.0.0 — Initial Release
- Push / Pull / Legs / Abs panels, day logging, streak counter, calendar, daily quote, mobile PWA
