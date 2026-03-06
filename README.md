<div align="center">

# ⚡ PPL Routine Tracker

**A mobile-first PWA for Push / Pull / Legs training with a Solo Leveling-inspired hunter stats system.**

Built for dumbbell-based training with an adjustable bench.

[![Version](https://img.shields.io/badge/version-1.3.3-4a9eff?style=flat-square&labelColor=03030e)](.)
[![PWA](https://img.shields.io/badge/PWA-ready-26c47a?style=flat-square&labelColor=03030e)](.)
[![Storage](https://img.shields.io/badge/storage-localStorage-7744ff?style=flat-square&labelColor=03030e)](.)

</div>

---

## 📁 Files

| File | Purpose |
|---|---|
| `index.html` | Workout tracker, routine editor, session logger |
| `hunter-stats.html` | Hunter stats — XP, levels, anime body diagram |

Deploy both to the same folder. They share data through `localStorage` and link to each other.

---

## ✨ Features

### 🏋️ Workout Panels (Push / Pull / Legs / Abs)
- Exercise cards with sets, reps, rest, and coaching cues
- Tap to expand full description; colored muscle tags in the header show targets at a glance
- Exercises grouped by muscle section within each day:
  - **Push:** Chest → Shoulders → Triceps
  - **Pull:** Back → Biceps → Forearms → Rear Delts
  - **Legs:** Warmup → Quads → Hamstrings → Glutes → Calves
  - **Abs:** Core Stability → Rectus Abdominis → Obliques

### ✏️ Inline Routine Editor
Tap the **pencil icon** on any panel to open the edit sheet — no code changes needed.

**Left column — Your workout**
- `↑ ↓` reorder within the same section · `✕` remove · inline **Sets / Reps / Rest** fields
- **⚡ Superset** toggle — pairs consecutive exercises within the same section; blocked across sections
- New exercises auto-slot into the correct section when added

**Right column — Exercise bank**
- 40+ exercises per day (including 7 individual warmup exercises for Legs), searchable by name or muscle
- Colored muscle tags and coaching cue preview on each card

### 📋 Live Routine Review
The tips box updates as you edit and flags:
- Sequencing issues (compounds before isolations)
- Volume warnings (too few exercises)
- Muscle overlap (same primary targeted 3+ times)
- Superset quality (same-section pairing enforced)

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
| `ppl_routines_v1` | Custom exercise order per day |
| `ppl_sr_v1` | Sets / reps / rest overrides |
| `ppl_ss_v1` | Superset pairings |

All data is local to your browser. Clearing browser storage resets everything.

---

## 📋 Patch Notes

### v1.3.3 — Legs Warmup as Individual Exercises + Gap Fix
- The single "Dynamic Warmup (8 min)" summary card replaced with 7 individual warmup exercises under their own **Warmup** section header, consistent with how Quads, Hamstrings, etc. are displayed:
  1. Seated Heel-to-Hip Switch
  2. 90/90 Hip Stretch
  3. Active Straight Leg Raise (ASLR)
  4. 90/90 to Hip Lift
  5. Kneeling Hip Flexor Lunge
  6. Deep Squat Hold
  7. Deep Lateral Lunge
- All 7 are available individually in the exercise bank and can be added/removed from the edit sheet like any other exercise
- Routine review compound/isolation checks now correctly exclude warmup exercises from sequencing analysis
- Migration runs automatically on first load — existing saved routines get the 7 warmup exercises prepended to Legs without losing any other customizations
- Fixed a rendering bug (extra closing tag in exercise cards) that caused a visual gap between the first and second exercise in every section

### v1.3.2 — UI Cleanup
- Removed redundant Primary/Secondary muscle text from inside expanded exercise cards
- Legs warmup restored as a standalone block (later replaced by v1.3.3 with individual exercises)
- Muscle Volume chart and session History removed from the Log tab

### v1.3.1 — Section Grouping + Superset Restrictions
- Exercises grouped by muscle section within each panel
- Adding from bank auto-slots into the correct section
- Reorder arrows blocked from crossing section boundaries
- Superset toggle blocked across sections
- Routine Review order summary removed

### v1.3.0 — Inline Routine Editor + Superset System + Live Review
- Pencil icon on each panel opens a two-column edit sheet
- Add, remove, reorder exercises and edit sets/reps/rest inline
- **⚡ Superset toggle** — mark consecutive exercises to render as a superset pair
- **Live Routine Review** — sequencing, overlap, and superset analysis
- All changes persist independently in separate localStorage keys

### v1.2.0 — Previous Day Logging
- Log a Previous Day widget in the Log tab

### v1.1.2 — Desktop Fix + Body Visibility
- Desktop scrolling fixed; Hunter Stats body visible at low levels

### v1.1.1 — Anime Body Diagram
- V-taper anatomy, Solo Leveling aesthetic, progressive muscle glow

### v1.1.0 — Hunter Stats Launch
- XP system, rank E→S, 11 muscle attributes, Quests + Feats tabs

### v1.0.0 — Initial Release
- Push / Pull / Legs / Abs panels, day logging, streak counter, calendar, daily quote, mobile PWA

### v1.3.4 — Larger Small Text
- Section titles (Chest, Shoulders, Quads, etc.) bumped from 0.62rem to 0.75rem
- Muscle tags on exercise cards bumped from 0.58rem to 0.68rem
- Exercise descriptions bumped from 0.80rem to 0.88rem with slightly more line height
- Rest labels, duration, focus label, superset label all bumped proportionally
- Routine Review text and edit sheet labels (column headers, sets/reps labels, bank preview text, superset hint) all increased to match
