# 🎼 MusicDL Engine (`musicdl-engine`)

**`musicdl-engine`** is one implementation of the **MusicDL Specification ([`musicdl-spec`](https://github.com/avinashsuresh1/musicdl-spec))**.

It provides the software parser, timeline scheduler, PCM synthesizer renderer, interactive Web Component desktop editor, and Web Audio / Tauri WASAPI native audio runtime written in TypeScript and Rust.

---

## 🚀 How to Get Started

### Prerequisites
* **Node.js**: version `v24.18.0` or higher.
* **Rust**: stable toolchain installed (via [rustup](https://rustup.rs/)).
* **Linux System Libraries** (if running or building on Linux):
  ```bash
  sudo apt-get install libasound2-dev
  ```
* **Windows**: Visual Studio C++ Build Tools or MinGW toolchain installed.

### 1. Run in Development Mode
To run the interactive desktop editor locally:
1. Open your terminal in `musicdl-engine` directory:
   ```bash
   npm install
   ```
2. Launch the desktop app:
   ```bash
   npx tauri dev
   ```

### 2. Run Tests
To run the automated vitest test suite:
```bash
npm test
```

### 3. Build Production App
To package into single desktop installers with zero runtime dependencies:
```bash
npm run tauri:build
```

---

## 📁 Architecture Overview

- **`src/types/`**: TypeScript interfaces for composition, instruments, melodies, chords, tracks, and scheduled notes.
- **`src/parser/`**: YAML parser (`yaml-parser.ts`), project serializer (`serializer.ts`), and strict schema validator (`validator.ts`).
- **`src/engine/`**: Timeline scheduler (`scheduler.ts`) and offline PCM audio synthesizer renderer (`renderer.ts`).
- **`src/state/`**: Reactive audio engine controller and application UI state management.
- **`src/components/`**: Modular Web Component UI components (timeline visualizer, code editor, instrument audition panel).
- **`src-tauri/`**: Native Rust Tauri desktop backend with WASAPI rodio real-time low-latency audio stream.
- **`tests/`**: Unit and integration vitest test suite.

---

## 🔗 Related Repositories

* **[`musicdl-spec`](https://github.com/avinashsuresh1/musicdl-spec)**: A YAML-based specification for music composition using text files and folders/directories.
