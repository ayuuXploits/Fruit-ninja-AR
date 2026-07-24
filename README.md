```
▗▄▄▄▖▗▄▄▖ ▗▖ ▗▖▗▄▄▄▖▗▄▄▄▖    ▗▖  ▗▖▗▄▄▄▖▗▖  ▗▖   ▗▖ ▗▄▖ 
▐▌   ▐▌ ▐▌▐▌ ▐▌  █    █      ▐▛▚▖▐▌  █  ▐▛▚▖▐▌   ▐▌▐▌ ▐▌
▐▛▀▀▘▐▛▀▚▖▐▌ ▐▌  █    █      ▐▌ ▝▜▌  █  ▐▌ ▝▜▌   ▐▌▐▛▀▜▌
▐▌   ▐▌ ▐▌▝▚▄▞▘▗▄█▄▖  █      ▐▌  ▐▌▗▄█▄▖▐▌  ▐▌▗▄▄▞▘▐▌ ▐▌
                                                      

```

<div align="center">

# Fruit-Ninja-AR

**Slice fruit in mid-air using nothing but your webcam and your index finger.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](./LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-Single_File-E34F26?style=for-the-badge&logo=html5&logoColor=white)](.)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![Babel](https://img.shields.io/badge/Babel-Standalone-F9DC3E?style=for-the-badge&logo=babel&logoColor=black)](https://babeljs.io)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-Hands-00A5E0?style=for-the-badge&logo=google&logoColor=white)](https://developers.google.com/mediapipe)
[![Canvas](https://img.shields.io/badge/Rendering-Canvas_2D-FF6F00?style=for-the-badge)](.)

[**🚀 Play It**](https://ayuuXploits.github.io/Fruit-ninja-AR/) &nbsp;·&nbsp; [**🐛 Report Bug**](https://github.com/ayuuXploits/Fruit-Ninja-AR/issues/new?labels=bug&title=%5BBug%5D+) &nbsp;·&nbsp; [**✨ Request Feature**](https://github.com/ayuuXploits/Fruit-Ninja-AR/issues/new?labels=enhancement&title=%5BFeature%5D+)

<br/>

*No controller. No touchscreen. No mouse. Just your hand, your webcam, and 17 kinds of fruit to slice.*

</div>

---

## ✨ Features

### 🖐️ Hand-Tracking Gameplay
- Real-time hand & finger tracking via **MediaPipe Hands** — no extra hardware needed
- Your index fingertip becomes the blade; its motion trail is checked every frame against every object on screen
- Supports **two hands at once**, each with its own independent trail

### 🎮 Three Game Modes
| Mode | Description |
|---|---|
| **Classic** | 3 lives, combo scoring, bombs to avoid |
| **Zen** | Relaxed slicing, no lives lost |
| **Arcade** | Timed high-score rush against the clock |

### 🍉 17 Slice-able Objects
Watermelon, orange, apple, banana, lemon, pineapple, mango, strawberry, peach, grapes, kiwi, cherry, blueberry, star, ice, diamond — and bombs to watch out for.

### ⚡ Power-Ups & Effects
- **Fever mode** — score multiplier on high combos
- **Freeze** — slows down falling objects
- **Double score** — temporary point boost
- Particle bursts, juice splatter stains, screen shake, and floating combo text on every slice

### 📊 Progress & Stats
- Persistent **high score**, saved to `localStorage`
- End-of-run stats screen: fruits sliced, fruits missed, max combo, best score
- Live bomb counter and heart-based lives display (Classic mode)

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Hand Tracking** | MediaPipe Hands + Camera Utils |
| **UI / Rendering** | React 18 (UMD build) |
| **JSX Transpiling** | Babel Standalone (in-browser, zero build step) |
| **Game Rendering** | HTML5 Canvas 2D |
| **Fonts** | Google Fonts — Boogaloo, Press Start 2P |
| **Persistence** | Browser `localStorage` |

No bundler. No `npm install`. No build pipeline — everything is loaded from CDNs at runtime, straight into a single `.html` file.

---

## 🗂️ Project Structure

```
Fruit-Ninja-AR/
├── AR_fruit_ninja.html   # Entire game — markup, styles, game loop, and rendering
├── README.md
├── LICENSE
└── .gitignore
```

Everything — the MediaPipe setup, React component, canvas game loop, particle system, and UI overlays — lives in one self-contained file for easy sharing and zero setup.

---

## 🚀 Getting Started

### Prerequisites
- A modern browser with WebRTC + WebGL support (Chrome recommended)
- A webcam
- Decent, even lighting (helps hand detection accuracy)

### 1. Clone the repository

```bash
git clone https://github.com/ayuuXploits/Fruit-Ninja-AR.git
cd Fruit-Ninja-AR
```

### 2. Run it

No install step required — just open the file directly:

```bash
open AR_fruit_ninja.html
```

Or serve it locally (recommended, since some browsers restrict camera access on `file://` URLs):

```bash
npx serve .
```

### 3. Play

1. Grant camera access when prompted.
2. Wait for **"Loading AI Models…"** to finish.
3. Pick a mode — **Classic**, **Zen**, or **Arcade**.
4. Raise your index finger and swipe through the air to slice!

---

## 🎮 Controls

| Action | How |
|---|---|
| Slice | Swipe your index finger through an object |
| Avoid | Don't slice bombs 💣 — costs a life in Classic mode |
| Menu | Return to main menu after Game Over |

---

## 🧑‍💻 Development Notes

- **Game state** is split between React `state` (for UI re-renders — score, lives, phase) and `refs` (for per-frame game logic — fruit positions, particles, timers) to keep the `requestAnimationFrame` loop fast and avoid unnecessary re-renders.
- **Slice detection** uses line–circle intersection math between consecutive finger-trail points and each object's hitbox.
- **MediaPipe results** are mirrored to match the horizontally-flipped webcam feed so the blade tracks correctly on screen.

---

## 📄 License

**Copyright © 2026 ayuuXploits. All rights reserved.**

Licensed under the [MIT License](./LICENSE).

---

<div align="center">

Built with ❤️ by [ayuuXploits](https://github.com/ayuuXploits)

</div>
