<div align="center">

# ⚡ PPL Routine Tracker

**A mobile-first PWA for Push / Pull / Legs training with a Solo Leveling-inspired hunter stats system.**

Built for dumbbell-based training with an adjustable bench.

[![Version](https://img.shields.io/badge/version-1.3.1-4a9eff?style=flat-square&labelColor=03030e)](.)
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
- Tap to expand full description and muscle targets
- Exercises are grouped by muscle section within each day:
  - **Push:** Chest → Shoulders → Triceps
  - **Pull:** Back → Biceps → Forearms → Rear Delts
  - **Legs:** Warmup → Quads → Hamstrings → Glutes → Calves
  - **Abs:** Core Stability → Rectus Abdominis → Obliques

### ✏️ Inline Routine Editor
Tap the **pencil icon** on any panel to open the edit sheet — no code changes needed.

**Left column — Your workout**
- `↑ ↓` reorder within the same section · `✕` remove · inline **Sets / Reps / Rest** fields
- **⚡ Superset** toggle — pairs consecutive exercises within the same muscle section; blocked across sections
- New exercises auto-slot into the correct section when added

**Right column — Exercise bank**
- 40+ exercises per day, searchable by name or muscle
- Same highlighted muscle tags as the main panels
- Coaching cue preview on each card

### 📋 Live Routine Review
The tips box updates as you edit and flags:
- Sequencing issues (compounds appearing after isolation work)
- Volume warnings (too few exercises)
- Muscle overlap (same primary targeted 3+ times)
- Superset quality (same-section pairs enforced — mismatched pairs are blocked at the source)

### 📅 Session Logging
- **Log today** — multi-group days stack (Legs + Abs on the same day both register)
- **Log a previous day** — backfill any date from the Log tab
- **Rest day** tracking
- **Delete** any history entry

### 📊 Log Tab
Streak counter · color-coded monthly calendar · 7-day muscle volume bars · 60-entry history

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

### v1.3.1 — Section Grouping + Superset Restrictions
- Exercises on each panel are now grouped by muscle section (e.g. Chest → Shoulders → Triceps on Push)
- Each exercise has an explicit section assignment based on primary emphasis; compound movements are grouped by the muscle they target most
- Adding an exercise from the bank auto-slots it into the correct section rather than appending to the bottom
- Reorder arrows are blocked from crossing section boundaries — exercises can only be shuffled within their own group
- Superset toggle now checks that an adjacent exercise shares the same section; blocked across sections with a toast notification
- Routine Review order summary removed — redundant given the visible exercise list

### v1.3.0 — Inline Routine Editor + Superset System + Live Review
- Pencil icon on each panel opens a two-column edit sheet — no separate tab required
- Add, remove, reorder exercises and edit sets/reps/rest inline
- **⚡ Superset toggle** — mark consecutive exercises to render as a superset pair
- **Live Routine Review** — replaces static tips with sequencing, overlap, and superset analysis
- All changes persist independently in separate localStorage keys
- Edit sheet matches main panel aesthetic (dark cards, colored muscle tags, day-accent border)
- Orphaned Build tab UI fully removed

### v1.2.0 — Previous Day Logging
- Log a Previous Day widget in the Log tab
- Date picker defaults to today; merges with existing entries

### v1.1.2 — Desktop Fix + Body Visibility
- Desktop scrolling fixed — natural page scroll at 768px+
- Hunter Stats body visible at low levels (tint from level 0)
- Abs grid lines visible from the start

### v1.1.1 — Anime Body Diagram
- V-taper anatomy, segmented abs, diamond calves
- Solo Leveling aesthetic: navy background, blue ambient glow, scan-line animation
- Eye glow scales with total sessions

### v1.1.0 — Hunter Stats Launch
- XP system, quadratic leveling, rank E→S
- 11 muscle attributes with SVG body diagram
- Quests + Feats tabs
- Multi-type logging, color-coded calendar, desktop sidebar

### v1.0.0 — Initial Release
- Push / Pull / Legs / Abs panels with 50 exercises
- Day logging, streak counter, calendar, session history
- Daily motivational quote, mobile PWA
