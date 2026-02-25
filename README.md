# Echo Show Keep-Alive for Home Assistant

A lightweight, dark-themed "Keep-Alive" page designed to prevent **Amazon Echo Show** devices from timing out and returning to the home screen when displaying Home Assistant dashboards.

## 🚀 The Problem
Echo Show devices are notorious for closing the Silk or Firefox browser after a few minutes of inactivity, even when displaying a Home Assistant dashboard via an Iframe.

## 💡 The Solution
This project uses a combination of techniques to keep the browser session active:
* **Audio Heartbeat:** Plays a media file (`media.mp3`) in a continuous loop.
* **DOM Updates:** A real-time clock and date display that refreshes every second to keep the rendering engine busy.
* **User Interaction:** Simple event listeners to unlock audio playback on the first touch.

## 🛠️ Installation

### 1. Upload Files
Upload the following files to your Home Assistant `www` folder (usually located at `/config/www/echo-keepalive/`):
* `index.html` (the code provided)
* `media.mp3` (any audio file; a silent track is recommended)

### 2. Add to Dashboard
Add a **Webpage Card** to your Home Assistant Lovelace dashboard with the following settings:

* **URL:** `/local/echo-keepalive/index.html`
* **Aspect Ratio:** 100% (or adjust to fit your specific Echo Show model)

---

## 📄 How to Use
1.  Open your dashboard on the Echo Show.
2.  **Crucial:** Tap the screen once. Due to modern browser autoplay policies, the "Keep-Alive" audio cannot start unmuted without a user gesture.
3.  The clock text will turn **yellow (#ffc107)** upon clicking, confirming that the audio is active and the "Keep-Alive" logic is running.

## 📂 File Structure
```text
/config/www/echo-keepalive/
├── index.html
└── media.mp3
```

##⚙️ Customization
Background: The background is set to #111111 to blend perfectly with Home Assistant's dark mode and save energy on the display.

Localization: The time and date are currently set to it-IT. You can change this in the index.html script section (e.g., to en-US or en-GB) by modifying the toLocaleTimeString and toLocaleDateString parameters.

Appearance: You can easily modify the CSS inside index.html to change font sizes or colors to match your personal dashboard style.
