<div align="center">

# ▶ SyncSubs

**Realtime SRT Subtitle Tracker**

[![License: MIT](https://img.shields.io/badge/License-MIT-10b981.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/Hosted_on-GitHub_Pages-0969da.svg)](https://asa07-salihg.github.io/SyncSubs/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-34d399.svg)](#contributing)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero-eab308.svg)](#)
[![PWA Ready](https://img.shields.io/badge/PWA-Ready-3b82f6.svg)](#)

<br>

A professional, zero-dependency subtitle tracker that runs entirely in your browser.
Load any `.srt` or `.vtt` file, play it in real-time, and fine-tune synchronization with millisecond precision.

**No installation. No backend. No tracking. Just subtitles.**

[**Live Demo**](https://asa07-salihg.github.io/SyncSubs/) · [**Report Bug**](../../issues/new) · [**Request Feature**](../../issues/new)

<br>

</div>

---

## ✨ Features

| | Feature | Description |
|---|---|---|
| 🎬 | **Real-time Playback** | SRT and WebVTT subtitles play in real-time with millisecond-accurate timing |
| 🎯 | **Precision Offset** | Shift subtitles from ±0.1s to ±10s with dedicated controls |
| 📊 | **Interactive Timeline** | Visual progress bar with click-to-seek and drag scrubbing |
| 🖱️ | **Drag & Drop** | Drop files directly onto the window, no file picker needed |
| 🔔 | **Toast Notifications** | Elegant feedback for file loads, errors, and state changes |
| 💾 | **Persistent Settings** | Font size, theme, language, and panel preferences survive page reloads |
| ♿ | **Full Accessibility** | ARIA labels, focus-visible rings, and complete keyboard navigation |
| 📱 | **Responsive Design** | Works beautifully on desktop, tablet, and mobile screens |
| 📦 | **PWA Ready** | Install as a native app; works offline with Service Worker caching |
| 🎨 | **Glassmorphism UI** | Stunning dark theme with frosted-glass panels and ambient gradients |
| 🚀 | **Zero Dependencies** | Pure HTML + CSS + JavaScript, nothing to install or build |
| 🌐 | **Multi-language** | 20 languages with a scrollable picker panel (EN, TR, ES, FR, DE, IT, PT, NL, SV, PL, UK, RU, AR, HI, TH, VI, ID, ZH, JA, KO) |
| 🌗 | **Light & Dark Theme** | Toggle between light and dark modes, preference saved automatically |
| 🔍 | **Subtitle Search** | Search through all loaded cues and jump to any match instantly |
| 📥 | **SRT Export** | Export your subtitle file with the current offset baked into timestamps |
| 🔀 | **Comparison View** | Load a second subtitle file and view both tracks side by side |

## 🚀 Quick Start

### Online

Visit the [**Live Demo**](https://asa07-salihg.github.io/SyncSubs/). No installation required. Your files are processed locally and never leave your device.

### Local

```bash
git clone https://github.com/asa07-salihg/altyazi.git
cd syncsubs

# Option A: Open directly
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux

# Option B: Local server (recommended for PWA)
npx serve .
```

### Install as PWA

1. Open the app in Chrome, Edge, or any Chromium-based browser
2. Click the **Install** icon in the address bar (or the browser menu)
3. Launch it from your home screen or app drawer, works offline

## 📖 How to Use

1. **Load a file** - Click the file button in the toolbar, or drag & drop a `.srt` / `.vtt` file anywhere on the screen
2. **Play** - Press the play button or hit `Space`
3. **Adjust timing** - Use the offset buttons on the bottom panel to shift subtitles forward or backward
4. **Customize** - Drag the font size slider or use `↑` / `↓` arrow keys
5. **Compare** - Click the `+` button to load a second subtitle file for side-by-side comparison
6. **Search** - Click the search icon or press `/` to find specific subtitle text
7. **Export** - Click the download button to export your SRT with the current offset applied
8. **Fullscreen** - Press `F` or click the fullscreen button for a distraction-free view
9. **Seek** - Click or drag on the timeline bar to jump to any position

## ⌨️ Keyboard Shortcuts

| Key | Action |
|:---|:---|
| `Space` | Play / Pause |
| `F` | Toggle Fullscreen |
| `R` | Reset (time + offset) |
| `←` or `,` | Offset -1 second |
| `→` or `.` | Offset +1 second |
| `↑` | Increase font size |
| `↓` | Decrease font size |
| `/` | Open subtitle search |
| `P` or `Esc` | Toggle offset panel |

## 🏗️ Architecture

SyncSubs is a single-file application optimized for GitHub Pages. The JavaScript is organized into focused classes:

```
┌─────────────────────────────────────────┐
│              App (Bootstrap)            │
├──────────────────┬──────────────────────┤
│   Player Engine  │     UI Manager       │
│  - Timing logic  │  - DOM rendering     │
│  - Cue lookup    │  - Event handling    │
│  - Offset math   │  - Drag & drop       │
│  - SRT export    │  - Timeline seek     │
│  - Dual tracks   │  - Search / theme    │
├──────────────────┼──────────────────────┤
│  SRT/VTT Parser  │  Lang / Toast / Stor │
│  - Robust regex  │  - i18n (20 langs)   │
│  - BOM tolerant  │  - Notifications     │
│  - WebVTT ready  │  - localStorage      │
└──────────────────┴──────────────────────┘
```

| Class | Responsibility |
|---|---|
| `SRTParser` | Robust `.srt` and `.vtt` parsing with BOM stripping, flexible timestamps (`,` and `.`), optional hours, and HTML sanitization |
| `Player` | Core timing engine with elapsed time tracking, dual-track cue lookup, offset math, and SRT export |
| `UI` | DOM rendering with RAF loop, drag & drop, timeline seeking, search, theme toggle, i18n, keyboard shortcuts |
| `Lang` | Lightweight i18n system supporting 20 languages with a scrollable selector panel |
| `Storage` | `localStorage` wrapper with graceful fallback for private browsing |
| `Toast` | Non-blocking notification system with auto-dismiss and click-to-close |

## 🤝 Contributing

Contributions are welcome and appreciated! Here's how you can help:

1. **Fork** the repository
2. **Create** your feature branch
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit** your changes
   ```bash
   git commit -m "Add amazing feature"
   ```
4. **Push** to the branch
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open** a Pull Request

### Implemented Features

- [x] Multi-language UI (i18n)
- [x] Light theme toggle
- [x] SRT file export with applied offset
- [x] Multiple file comparison view
- [x] WebVTT format support
- [x] Subtitle search / filter

### Future Ideas

- [x] Additional languages (20 languages with scrollable picker)
- [ ] Subtitle editing and inline timestamp correction
- [ ] Audio/video file pairing for synced playback
- [ ] Cloud sync for user preferences
- [ ] Plugin/extension system

## 🛠️ Tech Stack

This project is built with **zero dependencies**: no frameworks, no build tools, no package managers.

| Technology | Usage |
|---|---|
| **HTML5** | Semantic structure, ARIA accessibility, FileReader API |
| **CSS3** | Custom properties, flexbox, backdrop-filter, CSS animations, light/dark themes |
| **JavaScript ES6+** | Classes, template literals, `requestAnimationFrame`, Service Worker |
| **PWA** | `manifest.json` + Service Worker for offline support |

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for details.

---

<div align="center">

Made with care by [**Salih**](https://github.com/asa07-salihg)

If you found this useful, consider giving it a ⭐

</div>
