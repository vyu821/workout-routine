# PPL Routine Tracker

A mobile-first PWA for tracking Push / Pull / Legs workouts, building custom routines, and gamifying your training progress with a Solo Leveling-inspired hunter stats system.

Built for dumbbell-based training with an adjustable bench. No gym membership, no barbell required.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | Main workout tracker and routine builder |
| `hunter-stats.html` | Hunter stats — XP, levels, muscle attribute diagram |

Deploy both files to the same folder (e.g. GitHub Pages). They link to each other.

---

## Features

### Workout Panels (Push / Pull / Legs / Abs)
- Each panel lists all exercises for that day with sets, reps, rest intervals, and coaching cues
- Tap any exercise card to expand the full description and target muscles
- Exercises auto-expand on desktop for easy reference
- A tip box at the top of each panel covers sequencing and time-saving supersets

### Logging
- **Log Today** — tap the log button on any panel to record that muscle group for the current day
- **Multi-group days** — log Legs and Abs on the same day; they stack rather than replace each other
- **Log a Previous Day** — in the Log tab, pick any past date and select what you trained. Merges with existing entries so you won't overwrite anything already logged
- **Rest Day** — marks the day without counting toward session streaks
- **Delete entries** — swipe to delete any history entry from the Log tab

### Log Tab
- **Streak counter** — current streak, total sessions, sessions this week
- **Calendar view** — color-coded dots show which muscle groups you trained each day; navigate months with the arrows
- **Muscle volume chart** — bar chart of every muscle group hit in the last 7 days
- **Session history** — last 60 entries with date, muscle groups, and delete button

### Build Tab (Custom Workout Builder)
The Build tab has three sub-sections:

**Exercise Bank**
- 40+ exercises across all four days (Push, Pull, Legs, Abs)
- Filter by muscle group or search by name or target muscle
- Each card shows primary and secondary muscles targeted, plus full coaching cues
- Tap `+` to add to your current workout; it turns to `✓` when added
- Cards already in your workout are highlighted with a purple border

**My Workout**
- Name your workout and build it by adding exercises from the bank
- Adjust sets and reps for each exercise inline — tap the input fields and type
- Remove individual exercises with the `✕` button or clear the whole workout
- **Muscle Coverage panel** shows every muscle group for the days represented in your workout, color-coded green (covered) or red (missing)
- **Suggestions** auto-generate based on gaps — it'll tell you which exercise to add for an uncovered muscle, and flag any redundancy if a muscle is hit 3+ times while others go untrained
- Save the workout to the Saved tab

**Saved Workouts**
- All saved workouts persist in localStorage
- Load any saved workout back into the builder to edit or review
- Delete saved workouts you no longer need

### Hunter Stats (`hunter-stats.html`)
- Tracks XP and levels for 11 individual muscle attributes (Chest, Back, Biceps, Triceps, Shoulders, Forearms, Quads, Hamstrings, Glutes, Calves, Core)
- Each logged session grants 10 XP to each muscle in that day's group
- Muscles visually fill in and glow on the anime-style body diagram as they level up
- Rank progression: E → D → C → B → A → S (Shadow Sovereign at 150 total sessions)
- **Quests tab** — daily, weekly, and milestone targets
- **Feats tab** — 14 unlockable achievements; new unlocks trigger a notification banner
- Blue scan-line animation and Solo Leveling aesthetic throughout

---

## How to Use

### Option 1 — GitHub Pages (recommended)
1. Fork or upload both HTML files to a GitHub repo
2. Go to **Settings → Pages** and set the source to the main branch root
3. Your app will be live at `https://yourusername.github.io/your-repo/`
4. On mobile: open the link in Safari (iOS) or Chrome (Android), tap **Share → Add to Home Screen** to install as a PWA

### Option 2 — Local
1. Download both files to the same folder
2. Open `index.html` in any browser
3. Data saves to `localStorage` automatically — no server or account needed

### Data Storage
All data lives in your browser's `localStorage` under the key `ppl_v3`. It persists across sessions on the same device and browser. Clearing browser data or using incognito mode will reset it. Saved workouts use the key `ppl_workouts_v1`.

---

## Patch Notes

### v1.2.1
- Exercise bank and custom workout builder added (Build tab)
- 40+ exercises covering all four training days with full coaching cues and muscle targeting
- Sets and reps are adjustable per exercise in the builder
- Muscle coverage analysis shows which muscles are hit and which are missing in your custom workout
- Smart suggestions recommend exercises to add for gaps and flag redundancy when muscles overlap
- Saved workouts persist in localStorage; can be loaded back and edited
- Filter and search in the exercise bank

### v1.2.0
- Log a Previous Day feature added to the Log tab
- Date picker defaults to today; selecting multiple muscle groups merges with any existing entry for that date
- Rest Day option available in the backlog widget

### v1.1.2
- Hunter Stats body diagram visibility improved at low levels — muscles now show a visible tint from level 0 rather than appearing near-black
- Abs grid lines always visible from the start; brighten and take on the attribute color as Core levels up
- Desktop layout for index.html fixed — page now scrolls naturally at 768px+ without inner scroll containers conflicting with the sticky top bar
- Sidebar nav uses `position:sticky` on desktop so it stays anchored while scrolling through exercise panels

### v1.1.1
- Anime body figure added to Hunter Stats with proper V-taper anatomy (wide shoulders, narrow waist, segmented abs, quad separation, diamond calves)
- Solo Leveling aesthetic: deep navy background, blue ambient glow, corner accent lines, scan-line animation
- Muscle regions fill and glow progressively — soft tint at level 1, colored fill at level 5, glow filter at level 10, max glow at level 20
- Eye glow scales with total sessions logged

### v1.1.0
- Hunter Stats companion page (`hunter-stats.html`) launched
- XP system: 10 XP per muscle group per session; quadratic leveling curve
- Rank system: E through S with unlock titles
- 11 muscle attributes with SVG body diagram and label connectors
- Quests tab: daily missions, weekly targets, milestone progression
- Feats tab: 14 unlockable achievements with unlock notifications
- Navigation link between index.html and hunter-stats.html
- Multi-type logging: Push + Abs or Legs + Abs now stack on the same day
- Calendar updated to show per-group color dots for multi-type days
- Schedule bar removed from workout panels (was misaligned after rest days)
- Desktop responsive layout with sidebar navigation

### v1.0.0
- Initial release
- Push, Pull, Legs, and Abs workout panels with 50 exercises
- Exercise cards with sets, reps, rest intervals, and coaching descriptions
- Day logging with rest day support
- Log tab with streak counter, monthly calendar, 7-day muscle volume chart, and session history
- Daily motivational quote
- Mobile PWA with bottom navigation, safe area insets, and home screen install support
