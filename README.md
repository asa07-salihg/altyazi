# 🎬 SRT Tracker

This project is an advanced subtitle (`.srt`) playback and synchronization tool optimized for mobile devices (especially Android). It runs entirely in your browser without the need for any backend server.

It is designed to read subtitles independently from videos, track their timing, or test synchronization (offset) on the go.

## ✨ Features

* **🚀 No Installation Required:** It consists of a single HTML file. Just open it in your browser. All processing happens client-side; your files are never uploaded to any server.
* **📱 Mobile-Friendly Design:** Features a safe-area supported, touch-friendly, and compact control bar that doesn't clutter your screen.
* **⏱️ Precise Synchronization (Offset):** If your subtitles are out of sync, you can easily shift them forward or backward in milliseconds (0.1s, 0.5s, 1s, 5s, 10s) using the buttons on the bottom panel.
* **🔤 Customizable Appearance:** Instantly change the subtitle font size using the slider in the top menu.
* **🖥️ Fullscreen Support:** Hide distractions and switch to fullscreen mode with a single click or by pressing the "F" key.
* **⌨️ Keyboard Shortcuts:** Convenient shortcuts are available for those using external keyboards.

## 🚀 How to Use?

1. Click the 📄 **File** icon in the top menu and select an `.srt` or `.txt` file from your device.
2. Once loaded, click the **Play (▶)** button to start the subtitles.
3. Use the slider at the top to adjust the font size to your liking.
4. If you need to adjust the subtitle timing, use the **⏪ Rewind** or **Fast Forward ⏩** buttons on the bottom panel.
5. Click the ⚙️ gear icon in the bottom right corner to toggle the visibility of the offset panel.

## ⌨️ Keyboard Shortcuts

For desktop or external keyboard users:

| Key | Action |
| :--- | :--- |
| `Space` | Play / Pause |
| `F` | Toggle Fullscreen Mode |
| `R` | Reset (Rewind to start and reset offset) |
| `,` (Comma) | Adjust offset by -1 second |
| `.` (Period) | Adjust offset by +1 second |

## 🛠️ Technologies Used

This project was built entirely with **Vanilla Web Technologies**:
* HTML5 (FileReader API)
* CSS3 (Flexbox, CSS Variables, Backdrop-filter)
* JavaScript (ES6, requestAnimationFrame)

---
*Developer Note: This project is perfectly suited for hosting on GitHub Pages. You can enable GitHub Pages in your repository settings to use the project as a live website.*
