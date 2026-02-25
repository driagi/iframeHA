
# Echo Show Keep‑Alive for Home Assistant

A lightweight, dark‑themed keep‑alive page designed to prevent **Amazon Echo Show** devices from timing out and returning to the home screen when displaying Home Assistant dashboards via an iframe.

## 🚀 The Problem
Echo Show devices automatically close the Silk or Firefox browser after a few minutes of inactivity, interrupting any Home Assistant dashboard displayed in a Webpage Card.

## 💡 The Solution
This project keeps the browser session active by using:

- **Audio Heartbeat** – continuously loops a media file (`media.mp3`), ideally a silent track.
- **DOM Updates** – a live time/date display updated every second to keep the rendering engine active.
- **User Interaction** – a single tap enables the unmuted audio, required by modern autoplay restrictions.

---

## 🛠️ Installation

### 1. Upload the Files
Upload the following files to your Home Assistant `www` directory  
(typically located at `/config/www/echo-keepalive/`):

- `index.html`
- `media.mp3` (a silent audio file is recommended)

### 2. Add to Your Dashboard
Create a **Webpage Card** in your Home Assistant dashboard:

- **URL:** `/local/echo-keepalive/index.html`  
- **Aspect Ratio:** `100%` (or adjust for your specific Echo Show model)

---

## 📄 How to Use

1. Open your dashboard on the Echo Show.  
2. **Tap the screen once.**  
   This is required to start audio playback due to browser autoplay policies.  
3. The clock text will turn **yellow (#ffc107)**, indicating that the keep‑alive logic is active.

---

## 📂 File Structure

```text
/config/www/echo-keepalive/
├── index.html
└── media.mp3
```
## ⚙️ Customization

### **Background**
The background color is set to `#111111` to blend seamlessly with Home Assistant's dark mode and help reduce display power consumption.

### **Localization**
Time and date formatting are configured for `it-IT` by default.  
You can change this by editing the `toLocaleTimeString()` and `toLocaleDateString()` settings inside `index.html`.

### **Appearance**
You can freely customize font sizes, colors, spacing, and overall layout by modifying the CSS section inside `index.html`.
