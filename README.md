# Twins

A pure ink-on-paper canvas animation: twin girls play a clapping game, break
into a run, one trips the other, they crack up laughing, and it ends in a
hug. Hand-drawn line aesthetic, off-white paper background, procedural
"boiling line" wobble on every stroke.

**Live:** https://twins-production-8eb2.up.railway.app

## Running locally

This is a single self-contained file — no build step, no dependencies.

- Double-click `index.html` to open it directly in a browser, or
- Serve it locally: `python3 -m http.server 8000` in this folder, then visit
  `http://localhost:8000`

## Controls

- **replay** — restart the animation from the beginning
- **loop: on/off** — toggle whether it repeats

## QA / scrubbing

`index.html` exposes a small deterministic API on `window.TWINS` for jumping
to any frame without waiting on real time:

```js
TWINS.seek(9.6)  // render the frame at 9.6s
TWINS.play()     // resume normal playback
TWINS.t()        // current time in seconds
TWINS.DUR        // total duration of one loop
```
