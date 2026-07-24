# 🍉 AR Fruit Ninja

A browser-based, webcam-powered Fruit Ninja clone. Slice fruit in mid-air using nothing but your index finger — no controller, no touchscreen, just hand tracking via your webcam.

## How it works

Your webcam feed is passed through [MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) to track hand landmarks in real time. The tip of your index finger becomes a "blade" — its motion trail is checked every frame for intersections with flying fruit (and bombs) rendered on an HTML5 canvas layered over the video feed.

The whole game — UI, game loop, physics, and rendering — runs client-side in a single HTML file, with React (via in-browser Babel/JSX) handling the interface and a `requestAnimationFrame` loop driving gameplay.

## Features

- **Hand-tracking slicing** — raise your index finger and swipe through the air to slice
- **Three game modes**
  - **Classic** — 3 lives, combo scoring, bombs to avoid
  - **Zen** — relaxed, no lives lost
  - **Arcade** — timed high-score rush
- 17 fruit/object types (watermelon, mango, diamond, bombs, and more), each with unique colors and glow effects
- Combo system, fever mode, freeze and double-score power-ups
- Particle effects, juice splatter, screen shake, and floating score text
- Persistent high score (saved to `localStorage`)
- Live stats screen (fruits sliced, missed, max combo, best score)

## Tech stack

| Piece | Library |
|---|---|
| Hand tracking | MediaPipe Hands + Camera Utils |
| UI / rendering | React 18 (UMD build) |
| JSX transpiling | Babel Standalone (in-browser, no build step) |
| Game rendering | HTML5 Canvas |
| Fonts | Google Fonts (Boogaloo, Press Start 2P) |

No bundler, no `npm install`, no build step — everything loads from CDNs at runtime.

## Running it

1. Open `AR_fruit_ninja.html` in a modern browser (Chrome recommended).
2. Grant camera access when prompted.
3. Wait for "Loading AI Models…" to finish.
4. Pick a mode and start slicing!

> Requires a webcam and a browser with WebRTC + WebGL support. Works best in good lighting with your hand clearly visible against the background.

## Controls

- **Index finger up** → acts as the blade
- **Swipe through fruit** → slice it
- **Avoid bombs** → slicing one costs you (in Classic mode)

## Project status

Single-file prototype — all logic, styling, and markup live in `AR_fruit_ninja.html` for easy sharing and zero setup.

## License

MIT License — all rights reserved to **ayuuXploits**. See [LICENSE](LICENSE) for details.
