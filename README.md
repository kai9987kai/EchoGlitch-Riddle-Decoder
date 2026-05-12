# EchoGlitch Riddle Decoder™ Advanced Lab

A single-file browser game where riddles are transformed into corrupted glitch signals, then decoded by the player. EchoGlitch combines classic riddle solving with visual ciphers, streaks, adaptive difficulty, achievements, local leaderboards, accessibility toggles, and custom riddle imports.

The project is built with plain **HTML, CSS, and JavaScript**. No framework, no build step, no backend, and no account system required.

---

## ✨ Features

### Core Gameplay

* Generate riddles from built-in riddle packs.
* Enter your own custom riddle text.
* Encrypt riddles into animated glitch output.
* Solve the hidden answer to gain score and build streaks.
* Use hints, decoding tools, and confidence feedback to improve your guess.
* Track score, streak, accuracy, combo multiplier, history, and leaderboard locally.

### Glitch Cipher Modes

EchoGlitch includes multiple visual corruption modes:

| Mode               | Description                                                                       |
| ------------------ | --------------------------------------------------------------------------------- |
| Echo Zalgo         | Adds combining marks, wide symbols, cuneiform fragments, and private-use markers. |
| Mirror Fog         | Reverses some words and adds directional text distortion.                         |
| Caesar Static      | Applies a Caesar-style letter shift with visible shift metadata.                  |
| Glyph Storm        | Injects abstract glyphs around the original text.                                 |
| Zero-Width Whisper | Adds invisible zero-width characters into the signal.                             |
| Hybrid Chaos       | Mixes multiple corruption methods across chunks of the riddle.                    |

### Difficulty System

Available difficulties:

* Easy
* Medium
* Hard
* Expert
* Adaptive

Adaptive mode increases difficulty as the player builds a higher streak.

### Riddle Packs

Built-in riddle categories include:

* Classic
* Logic
* Nature
* Tech
* Custom Only
* All Signals

### Advanced Decoder Tools

* **Decode Lens** strips visual glitch markers and displays a cleaned version of the corrupted text.
* **Smart Hints** provide progressive clue levels.
* **Fuzzy Answer Check** accepts close spellings and small typos.
* **Confidence Meter** estimates how close the current guess is to the correct answer before submitting.
* **Daily Signal** generates a daily-style riddle challenge.

### Player Progression

The game tracks:

* Score
* Current streak
* High streak
* Accuracy
* Combo multiplier
* Solve history
* Local leaderboard
* Achievements
* Used cipher modes
* Custom riddle packs

All progress is saved in browser `localStorage`.

### Achievements

Current achievements include:

* **Riddle Rookie** — solve your first riddle.
* **Streaker** — reach a 5-riddle streak.
* **Mastermind** — solve 20 riddles.
* **Glitch Hunter** — use every cipher mode.
* **No-Hint Ninja** — solve a hard or expert riddle without hints.
* **Speed Echo** — solve a riddle in under 10 seconds.
* **Custom Crafter** — import a custom riddle pack.

### Accessibility and Comfort Options

* Light and dark theme.
* Reduced motion mode.
* High contrast mode.
* Optional generated sound blips.
* Keyboard shortcuts.
* Large controls and readable panels.
* Safer text rendering using `textContent` for glitch output.

---

## 🚀 Quick Start

### Option 1: Open Directly

1. Download or clone the project.
2. Open `index.html` in a modern browser.
3. Click **Generate Riddle**.
4. Click **Encrypt Glitch**.
5. Type your answer and click **Solve & Decrypt**.

### Option 2: Run with a Local Server

This project works as a static file, but a local server is useful for development.

Using Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Using Node.js:

```bash
npx serve .
```

---

## 🎮 How to Play

1. Choose a **difficulty**, **riddle pack**, and **glitch cipher**.
2. Click **Generate Riddle** or write your own riddle.
3. Adjust **Glitch Intensity**.
4. Click **Encrypt Glitch**.
5. Read the corrupted signal and guess the answer.
6. Use **Smart Hint** or **Decode Lens** if needed.
7. Submit your answer with **Solve & Decrypt**.
8. Build streaks, unlock achievements, and climb the local leaderboard.

---

## ⌨️ Keyboard Shortcuts

| Key     | Action                                 |
| ------- | -------------------------------------- |
| `G`     | Generate riddle                        |
| `E`     | Encrypt glitch                         |
| `Enter` | Solve when focused in the answer input |
| `H`     | Use hint                               |
| `L`     | Activate Decode Lens                   |

---

## 📦 Project Structure

The current version is designed as a single-file web app:

```text
EchoGlitch-Riddle-Decoder/
├── index.html
└── README.md
```

Everything is contained inside `index.html`:

* HTML layout
* CSS theme system
* Game logic
* Cipher logic
* Scoring
* Achievements
* Local storage save data
* Import/export tools

---

## 🧩 Importing Custom Riddles

Click **Import Riddles** and paste a JSON array.

Example:

```json
[
  {
    "riddle": "What runs but never walks?",
    "answer": "water",
    "difficulty": "easy",
    "category": "nature",
    "aliases": ["a river", "river"]
  },
  {
    "riddle": "I protect secrets by turning meaning into symbols. What am I?",
    "answer": "cipher",
    "difficulty": "hard",
    "category": "tech",
    "aliases": ["encryption", "code"]
  }
]
```

Required fields:

| Field        | Required | Description                                                                    |
| ------------ | -------- | ------------------------------------------------------------------------------ |
| `riddle`     | Yes      | The riddle text shown to the player.                                           |
| `answer`     | Yes      | The correct answer.                                                            |
| `difficulty` | No       | `easy`, `medium`, `hard`, or `expert`.                                         |
| `category`   | No       | Any category name, commonly `classic`, `logic`, `nature`, `tech`, or `custom`. |
| `aliases`    | No       | Alternative accepted answers.                                                  |

Invalid entries are ignored during import.

---

## 💾 Local Storage

EchoGlitch stores progress locally in the browser.

Main storage key:

```text
echoglitch-advanced-v2
```

The game may also migrate older keys:

```text
achievements
leaderboard
highStreak
```

Stored data can include:

* Player name
* Score
* Streaks
* Accuracy
* Leaderboard entries
* Achievements
* Custom riddles
* Settings
* Solve history

Use **Export Progress** to download a JSON backup of the current save data.

Use **Reset Local Data** to clear saved progress.

---

## 🧠 Scoring System

Score is affected by:

* Difficulty level
* Glitch intensity
* Combo multiplier
* Solve speed
* Daily Signal bonus
* Hint penalty
* Fuzzy-match penalty

Harder riddles, stronger glitch intensity, faster solves, and longer streaks produce higher scores.

---

## 🧪 Notable Technical Ideas

### Visual Cipher Layer

The game uses multiple lightweight text transformation methods:

* Combining Unicode marks
* Directional text controls
* Caesar-style shifts
* Abstract glyph injection
* Zero-width characters
* Hybrid chunk corruption

### Safer Rendering

The upgraded output avoids directly inserting user-controlled riddle text as HTML. Glitched text is rendered using `textContent`, reducing accidental markup injection risks when players use custom riddles.

### Local Similarity Matching

Fuzzy answers are checked with local string normalization and Levenshtein-style similarity scoring. This allows small typos without requiring external APIs.

### Browser-Only Progression

No server is needed. Achievements, history, settings, and custom riddles are stored through `localStorage`.

---

## 🎨 Customization Ideas

You can easily customize:

* Riddle list
* Categories
* Difficulty multipliers
* Scoring formula
* Achievement conditions
* Cipher modes
* CSS theme variables
* Button layout
* Local storage key
* Import/export format

Useful places to edit:

```js
const baseRiddles = [...]
const achievementsCatalog = {...}
function transformText(text, mode, intensity, rand) {...}
function calculateScore(seconds, fuzzyAccepted) {...}
```

---

## 🛠️ Troubleshooting

### The page opens but nothing happens

Make sure JavaScript is enabled in your browser.

### Clipboard copy does not work

Some browsers block clipboard access on local files. Try running the project through a local server.

### My imported riddles do not appear

Check that your JSON is valid and that every riddle has both `riddle` and `answer` fields.

### Animations feel too intense

Enable **Reduced Motion** in the Decoder Lab panel.

### The text is hard to read

Enable **High Contrast** or reduce the glitch intensity slider.

### I want a clean save

Use **Reset Local Data** to clear browser-stored progress.

---

## 🧭 Roadmap Ideas

Potential future upgrades:

* Puzzle campaign mode.
* Timed challenge mode.
* Multiplayer local party mode.
* Procedural riddle generator.
* More cipher families.
* Shareable challenge codes.
* Visual timeline of solve history.
* Hint cost preview.
* Difficulty calibration based on player accuracy.
* PWA offline install support.
* Optional Web Speech reading mode.
* Animated cipher explanation panel.
* Riddle editor with validation.
* Theme presets and custom accent color picker.

---

## 🔒 Privacy

EchoGlitch does not require a login or backend. Progress is stored locally in the browser. Imported riddles and leaderboard data stay on the current device unless manually exported.

---

## 🤝 Contributing

Ideas, bug fixes, and new riddle packs are welcome.

Suggested contribution areas:

* Add more riddles.
* Improve accessibility.
* Add new cipher modes.
* Improve scoring balance.
* Add mobile layout refinements.
* Create new themes.
* Add tests for answer matching and import validation.

---

## 📄 License

Add your preferred license here.

Common options:

* MIT License for open reuse.
* GPL if you want derivative works to stay open source.
* All Rights Reserved if you do not want reuse without permission.

---

## Project Summary

**EchoGlitch Riddle Decoder™ Advanced Lab** is a creative browser puzzle experiment that turns simple riddles into corrupted glitch signals. It mixes wordplay, pattern recognition, Unicode visual distortion, local progression systems, and accessible game controls into a compact single-file web app.
