# 🎉 Merch Overlay (Streamer.bot / OBS HTML Overlay)

A clean animated merch overlay that:

* Displays a PNG (`merch_static.png`)
* Fades in → gently sways → fades out
* Includes a subtle blue glow (no box outline issues)
* Automatically loops every 5 minutes
* Works locally in OBS (no server required)

---

## 📂 Folder Structure

Make sure your files are set up like this:

```
/Merch_Overlay/
  ├── merch_overlay.html
  └── merch_static.png
```

---

## 🖥️ OBS Setup

1. Add a **Browser Source** in OBS
2. Set URL to:

```
file:///C:/PATH/TO/Merch_Overlay/merch_overlay.html
```

3. Recommended settings:

* ✔ Shutdown source when not visible
* ✔ Refresh browser when scene becomes active

---

## ✨ Features

* Smooth fade-in animation
* Gentle sway movement
* Soft blue glow (optimized to avoid square edges)
* Fully automatic loop (every 5 minutes)
* Lightweight (no external dependencies)

---

## 🎨 Customization

### 🔵 Adjust Glow Strength

Edit this in the HTML:

```css
filter: drop-shadow(0 0 5px rgba(0,180,255,0.3));
```

Examples:

**Less glow (very subtle):**

```css
filter: drop-shadow(0 0 4px rgba(0,150,255,0.25));
```

**More glow:**

```css
filter: drop-shadow(0 0 12px rgba(0,150,255,0.6));
```

---

### ⏱ Change Display Time

Find this line:

```javascript
300000
```

This equals **5 minutes**.

Examples:

* 1 minute → `60000`
* 10 minutes → `600000`

---

### 🎞 Disable Fade Out (always visible)

Remove this block:

```javascript
hideTimer = setTimeout(() => {
  clearTimers();
  fadeOut();
}, 300000);
```

---

### 🎯 Change Sway Motion

Edit this:

```javascript
const angles = [-3, 2.5, -2, 1, 0];
```

* Bigger numbers = more movement
* Smaller numbers = more subtle

---

## 🧪 Troubleshooting

### ❌ Image not showing

* Check file name: `merch_static.png`
* Ensure it's in the same folder as HTML
* Make sure extension is not duplicated (`.png.png`)

---

### ❌ Glow shows a square box

* Lower glow blur:

```css
drop-shadow(0 0 5px rgba(0,180,255,0.3))
```

* Ensure PNG has proper transparency

---

### ❌ Overlay not refreshing

* Enable **Refresh browser when scene becomes active** in OBS

---

## 🚀 Future Ideas

* Sound effect on appearance
* Glow pulse or color cycling
* Queue system for multiple alerts
* Dynamic glow color based on events

---

## ❤️ Credits

Created for Streamer.bot + OBS overlays
Custom-built for smooth performance and clean visuals

---

Enjoy your merch overlay! 🎮🔥
