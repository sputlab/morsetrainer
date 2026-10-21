# MorseTrainer

[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](LICENSE)
[![Release](https://img.shields.io/badge/release-v1.0.1-2dd4bf.svg)](https://github.com/sputlab/morsetrainer/releases)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-brightgreen.svg)](#)
[![Web Audio API](https://img.shields.io/badge/Audio-Web%20Audio%20API-orange.svg)](#)
[![Platform](https://img.shields.io/badge/Platform-Web%20Browser-blue.svg)](#)

An elegant, browser-based Morse code translator, interactive keyer, and learning trainer built entirely with modern web technologies and the **Web Audio API**.

Created by [Sputlab.com](https://www.sputlab.com).

---

## ✨ Features

- **🔄 Bidirectional Morse Translation**
  - Instant text-to-Morse and Morse-to-text decoding.
  - Real-time visual representation showing colored dots (`·`) and dashes (`—`).
  - Highlights unrecognized characters for easy debugging.

- **🔊 Web Audio Tone Synthesizer**
  - Smooth sine-wave oscillator audio playback with soft ramp anti-click envelopes.
  - Synchronized visual playback highlighting symbols in real time.
  - Configurable transmission speed: **5 to 40 WPM** (Words Per Minute).
  - Configurable sidetone frequency: **300 Hz to 1000 Hz** (default 650 Hz).

- **⚡ Interactive Keyer (Practice Paddle)**
  - Transmit Morse code manually using touch, mouse click, or the **Spacebar**.
  - Dynamic timing progress bar with visual markers for dot vs. dash thresholds.
  - Automatic letter commit (3 units of silence) and word space insertion (7 units).
  - Live statistics: dots sent, dashes sent, characters formed, and timing accuracy score.

- **🎯 Target Training Mode**
  - Gamified speed and accuracy drill mode.
  - Generates random alphanumeric targets for you to key in.
  - Instant visual flash feedback (correct / incorrect) and score counter.

- **📖 Reference Guide & Alphabet Chart**
  - Interactive lookup table for letters (A–Z), digits (0–9), and punctuation marks.
  - Visual dot/dash diagram and explanation of the International Morse Code timing standard.

- **📱 Sleek, Mobile-First Dark UI**
  - Responsive design optimized for both mobile smartphones and desktop screens.
  - Zero external dependencies, build tools, or frameworks required.

---

## 🚀 Getting Started

### 1. Run Locally
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

| Action | Control | Tab |
|---|---|---|
| **Keyer Pad** | Press & hold mouse / tap screen / hold <kbd>Space</kbd> | Keyer |
| **Clear Keyer Output** | Click `Clear` button | Keyer |
| **Play Tone** | Click `▶ Play audio` button | Translator |
| **Stop Audio** | Click `■ Stop` button | Translator |
| **Speed (WPM)** | Adjust top slider (5 – 40 WPM) | All |
| **Sidetone Pitch (Hz)** | Adjust top slider (300 – 1000 Hz) | All |

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
├── index.html                  # Main application entry point (v1.0.1)
├── .gitignore                  # Git ignore rules
├── CONTRIBUTING.md             # Contribution guidelines
├── LICENSE                     # MIT License
└── README.md                   # Documentation
```

---

## 🌐 Deploy to GitHub Pages

1. Go to your repository on GitHub.
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
