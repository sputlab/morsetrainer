# MorseTrainer

[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](LICENSE)
[![Release](https://img.shields.io/badge/release-v1.1.0-2dd4bf.svg)](https://github.com/sputlab/morsetrainer/releases)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-brightgreen.svg)](#)
[![Web Audio API](https://img.shields.io/badge/Audio-Web%20Audio%20API-orange.svg)](#)
[![Platform](https://img.shields.io/badge/Platform-Web%20Browser-blue.svg)](#)

An ultra-responsive, browser-based Morse code translator, interactive keyer paddle, and learning trainer built with modern web standards and the **Web Audio API**.

Created by [Sputlab.com](https://www.sputlab.com).

---

## ✨ Features & Architecture Highlights

- **⚡ Ultra-Low Latency Audio & Input Engine**
  - Interactive `AudioContext` with hardware-optimized buffer size (`latencyHint: "interactive"`).
  - Pre-warmed audio pipeline eliminates cold-start audio latency on mobile and desktop.
  - Smooth anti-click attack and exponential release envelopes for pure, pop-free sidetones.

- **🚀 60 / 120 FPS Zero-Reflow Keyer**
  - Visual timing progress bar powered by GPU-accelerated CSS transforms (`transform: scaleX()`).
  - Zero layout recalculations (reflows) during active keying.
  - **Adaptive Sleep Loop**: Animation loop automatically pauses when idle to consume 0% CPU and preserve battery life.

- **🔄 Bidirectional Morse Translation**
  - Instant text-to-Morse and Morse-to-text decoding.
  - Single-pass `DocumentFragment` DOM rendering prevents stutter even when pasting long text.
  - Visual dot (`·`) and dash (`—`) symbol representation with duration estimates.
  - Unknown/unsupported character highlighting.

- **🔊 Audio-Clock Synchronized Visual Playback**
  - High-precision symbol highlighting locked directly to the hardware audio clock (`AudioContext.currentTime`).
  - Eliminates timer drift and desynchronization.
  - Independent volume control (0% – 100%).
  - Adjustable speed: **5 to 35 WPM**.
  - Adjustable pitch: **300 Hz to 1000 Hz** (default 650 Hz).

- **⚡ Interactive Keyer (Manual Paddle)**
  - Transmit Morse code using touch, mouse click, or the <kbd>Spacebar</kbd>.
  - Pointer capture support with automatic blur and cancellation protection.
  - Built-in **Backspace** feature (button & <kbd>Backspace</kbd> key) to delete the last keyed character.
  - Sub-millisecond timing tracking: dots sent, dashes sent, character count, and precision percentage score.
  - Subtle mobile haptic feedback on supported devices.

- **🎯 Target Training Mode**
  - Gamified speed and accuracy drill mode.
  - Generates non-repeating random alphanumeric targets to key in.
  - Instant visual flash feedback and live score counter.

- **📖 Interactive Guide & Alphabet Chart**
  - Complete international Morse alphabet chart (A–Z, 0–9, punctuation).
  - **Interactive audio preview**: Click or tap any character in the table to instantly hear its Morse tone.

- **📱 Mobile-First Responsive PWA Experience**
  - Dark-mode interface designed with high contrast and touch-friendly targets.
  - Zero external dependencies, build tools, or frameworks required.

---

## 🚀 Getting Started

### Run Locally
No build process or dependencies required! Simply clone the repository and open `index.html` in your browser:

```bash
# Clone the repository
git clone https://github.com/sputlab/morsetrainer.git

# Open index.html directly in your default browser
open index.html   # On macOS
# xdg-open index.html # On Linux
# start index.html   # On Windows
```

Or run a lightweight local static server:

```bash
# Python 3
python3 -m http.server 8000

# Node.js
npx serve .
```

Then visit `http://localhost:8000`.

---

## ⌨️ Controls & Shortcuts

| Action | Control / Shortcut | Tab |
|---|---|---|
| **Keyer Pad** | Press & hold mouse / tap screen / hold <kbd>Space</kbd> | Keyer |
| **Backspace** | Click `⌫ Backspace` / press <kbd>Backspace</kbd> | Keyer |
| **Clear Keyer Output** | Click `Clear` button | Keyer |
| **Play Tone** | Click `▶ Play` button | Translator |
| **Stop Audio** | Click `■ Stop` button | Translator |
| **Copy Morse** | Click `Copy Morse` button | Translator |
| **Sound Preview** | Click any character card | Guide |
| **Speed (WPM)** | Adjust top slider (5 – 35 WPM) | All |
| **Pitch (Hz)** | Adjust top slider (300 – 1000 Hz) | All |
| **Volume (%)** | Adjust top slider (0 – 100%) | All |

---

## 📐 Morse Timing Fundamentals

Morse code timing is normalized to the duration of one **unit** (the length of a dot):

$$\text{Unit Duration (ms)} = \frac{1200}{\text{WPM}}$$

- **Dot (`·`)**: 1 unit
- **Dash (`—`)**: 3 units
- **Intra-character gap**: 1 unit (between dots/dashes of the same letter)
- **Inter-character gap**: 3 units (between letters)
- **Word gap**: 7 units (between words)

At 15 WPM, 1 unit equals 80 ms.

---

## 📂 Project Structure

```text
morsetrainer/
├── .github/
│   ├── workflows/
│   │   └── deploy.yml          # Automated GitHub Pages deployment
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md       # GitHub issue template for bugs
│   │   └── feature_request.md  # GitHub issue template for ideas
│   └── PULL_REQUEST_TEMPLATE.md
├── index.html                  # Main application entry point (v1.1.0)
├── .gitignore                  # Git ignore rules
├── CONTRIBUTING.md             # Contribution guidelines
├── LICENSE                     # MIT License
└── README.md                   # Documentation
```

---

## 🌐 Deploy to GitHub Pages

1. Go to your repository on GitHub: `https://github.com/sputlab/morsetrainer`.
2. Navigate to **Settings** > **Pages**.
3. Under **Build and deployment** > **Source**, choose **GitHub Actions** (the included `.github/workflows/deploy.yml` will automatically build and publish on every push to `main`).
   - Alternatively, choose **Deploy from a branch** and select `main` / `/ (root)`.

---

## 🤝 Contributing

Contributions, feedback, and feature suggestions are welcome! Please check out [CONTRIBUTING.md](CONTRIBUTING.md) to get started.

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

Developed with ❤️ by [Sputlab.com](https://www.sputlab.com).
