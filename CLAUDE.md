# Twins — Re-Entry File

## What This Is
A pure black-ink-on-paper animation: twin 13-year-old girls play a clapping
game, break into a run, one trips the other, they crack up laughing, and it
ends in a hug. All off-white (#efece3) and black (#171310), hand-drawn line
aesthetic. One self-contained file — no frameworks, no build, no server logic.

## Re-Entry Phrase
"Re-entry: Twins"

## Current Status
✅ v1 complete — full 18.5s story verified beat-by-beat in preview.

## How to Run
Open `index.html` in any browser (double-click works — no server needed).
Dev server: `python3 -m http.server 5581` in this folder, or the `twins`
entry in `~/.claude/launch.json` (Preview tool).

## The Story (timeline)
- 0.0–4.0 clapping game (facing each other, patty-cake rhythm)
- 4.0–4.8 turn to run
- 4.8–8.2 the chase — A starts behind and closes the gap
- 8.2–9.6 A sticks a foot out → B tumbles → lands seated; A's hand → mouth "oh!"
- 9.6–13.0 both crack up — A doubles over hands-on-knees, B rocks on the ground
- 13.0–15.0 A offers a hand, B rises
- 15.0–18.5 hug — heads cheek-to-cheek, arms crossed around backs, gentle sway
Loops by default (paper-fade at the seam); replay + loop buttons bottom center.

## How It Works (single file: index.html)
- Canvas 2D, 1600×900 design space, ground y=700, camera pan+1.38 zoom.
- Figures = 2-bone limb chains drawn with `inkLine()` — every stroke gets a
  quantized 6fps "boiling line" wobble so it feels hand-drawn.
- Angle convention: 0 = straight down, POSITIVE rotates toward the facing
  direction. ⚠️ Negative shoulder = arm swings BACKWARD (bit me once).
- Poses per story segment are functions of local time; segments blend with
  `mixPose`. Run cycle is procedural (`runPose`), the trip is keyframed.
- Twin marker: ponytail side (girl A left, girl B right). Faces: dot eyes /
  happy-arc eyes + laugh mouth / "oh" mouth.
- **QA scrub API**: `window.TWINS.seek(sec)` renders any frame deterministically
  (this is how to verify in the headless preview where rAF barely ticks);
  `.play()`, `.t()`, `.DUR`.

## GitHub
papjamzzz/twins

## Last Session (2026-07-02)
Built start to finish. Fixed along the way: arm-sign convention (clap/hug/help
arms initially raised backward), seek-vs-rAF race, trip causality (A now closes
the run gap so the foot actually reaches B), camera clamp at the laugh scene,
sun now fixed in frame, hug arms rewrapped low around waists + heads separated
to cheek-to-cheek. All 7 beats screenshot-verified, zero console errors.
NEXT if wanted: sound (giggle/footsteps), a second camera pass (slight push-in
on the hug), export as video/GIF.
