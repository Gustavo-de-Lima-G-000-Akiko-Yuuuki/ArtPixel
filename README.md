
# 💔 ArtPixel

Simple, I created it based on a GitHub post on LinkedIn, thinking I might find it a job and/or demand. I created it on October 1, 2025, the day I resigned from my job.
---

This project implements a retro CRT-style interface with animated pixel art.
The animation is rendered on a canvas using frames described in JSON, allowing you to create custom pixel art-style animations.
---

**👉 Try it live here**: [web](https://gustavo-de-lima-g-000-akiko-yuuuki.github.io/ArtPixel.github.io/)

# ORIGINAL:
![Descrição do GIF](https://github.com/Gustavo-de-Lima-G-000-Akiko-Yuuuki/ArtPixel.github.io/blob/main/gif%20original.gif?raw=true)


# DIY:
![Descrição do GIF](https://github.com/Gustavo-de-Lima-G-000-Akiko-Yuuuki/ArtPixel.github.io/blob/main/gif%20diy.gif?raw=true)

## 📂 Project Structure

```
/
├── index.html # Main application file
├── pixelart_frames_72x56_full.json # File containing the animation frames
├── /assets # (optional) Folder for other resources
└── README.md # Project documentation
```

---

## 📖 Technical Operation

### 1. HTML Structure
- The HTML defines a **retro CRT frame** containing:
- `canvas` (`id="arte"`) where the animation is drawn.
- Visual effects such as scanlines, light edges, and screen shake.
- A **status footer** with animated text `"Thinking..."`.

### 2. CSS Style
- Using CSS variables (`:root`) to define the color palette.
- Effects:
- Glow CRT (`box-shadow`, `drop-shadow`).
- Scanlines (`repeating-linear-gradient`).
- Flicker (`@keyframes tremor`).
- Smooth interface input (`@keyframes input`).

### 3. Color Palette
The palette is defined in a JavaScript object that maps symbols to colors:

```js
const colorPalette = {
'k': '#0b0b10', // black
'P': '#b66bff', // light purple
'p': '#a455f7', // dark purple
'B': '#77c7ff', // light blue
'b': '#5bb1ef', // dark blue
'G': '#8ef1a0', // green
'W': '#ffffff', // white
'.': null // transparent
};
```

Each frame of the animation is represented as a **character array**, where each symbol corresponds to a color.

### 4. Animation
- The script loads `pixelart_frames_72x56_full.json` via **fetch API**. - The `iniciarAnimacao` function controls the cycle:
- `desenhar()` – Renders a frame on the canvas.
- `requestAnimationFrame` – Synchronizes frames at the configured rate (`FPS = 30`).
- Automatic adjustment to window resize.

---

## 🖼️ How to Create New Frames

Each frame is a two-dimensional array in JSON:

```json
[
["k","k","k","B","B"],
["k","P","P","B","k"],
["k","p","p","B","k"],
["k","k","k","k","k"]
]
```

- Each string is a symbol from the palette (`k`, `P`, `p`, `B`, etc.). - The canvas is automatically resized to the width/height of the frame.

---

## ▶️ How to Run

1. Clone the repository or copy the files:
```bash
git clone https://github.com/yourusername/artpixel.git
cd artpixel
```

2. Make sure `index.html` and `pixelart_frames_72x56_full.json` are in the same folder.

3. Open the `index.html` file in the browser.

---

## ⚙️ Optional Settings

- **FPS**: Can be adjusted in the script constant:
```js
const FPS = 30; // Change to 60 for smoother animation
```

- **Colors**: Add or modify symbols in the `paletaCores` object.

- **Size**: By changing the frame JSON, the pixel art resolution is also automatically adjusted.

---

## 📌 Accessibility
- The `role="img"` and `aria-label` have been added for screen readers.
- The `canvas` has `aria-hidden="true"` to avoid interfering with assistive navigation.

---

## ✨ Author
Project developed by **Gustavo Lima G (AKIKO_YUUKI)**.
