# Echo Show Keep-Alive for Home Assistant

A lightweight, dark-themed "Keep-Alive" page designed to prevent **Amazon Echo Show** devices from timing out and returning to the home screen when displaying Home Assistant dashboards.

## 🚀 The Problem
Echo Show devices often close the browser (Silk or Firefox) after a few minutes of inactivity, even when displaying a Home Assistant dashboard.

## 💡 The Solution
This project uses a hosted "heartbeat" page to keep the browser session active:
* **Audio Heartbeat:** Plays a silent media file in a continuous loop.
* **DOM Updates:** A real-time clock and date display that refreshes every second to keep the rendering engine active.
* **Visual Feedback:** The clock turns **yellow** once activated to confirm the keep-alive script is running.

## 🛠️ How to Use with Home Assistant

You don't need to host any files locally. You can link directly to the hosted version.

### 1. Add a Webpage Card
Add a **Webpage Card** (Iframe) to your Home Assistant Lovelace dashboard with the following settings:

* **URL:** `https://driagi.github.io/iframeHA/`
* **Aspect Ratio:** 100% (or adjust to fit your specific Echo Show model)

### 2. Interaction (Crucial)
1. Open your dashboard on the **Echo Show**.
2. **Tap the screen once** on the clock area. 
3. Because of modern browser policies, audio/looping scripts cannot start "unmuted" without a user gesture. 
4. Once you tap, the text color will change to **yellow (#ffc107)**, confirming that the "Keep-Alive" logic is now active.

---

## ⚙️ Features
* **Dark Mode:** Background set to `#111111` to blend perfectly with Home Assistant's dark themes and save energy.
* **Zero Maintenance:** Hosted on GitHub Pages; no need to manage local `.mp3` or `.html` files in your `/config/www/` folder.
* **Localization:** Displays time and date in `it-IT` format.

---

*Note: This tool is a community workaround for Amazon's aggressive power-saving features. Performance may vary based on your Echo Show firmware version.*
