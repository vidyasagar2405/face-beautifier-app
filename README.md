# Face-Beautifier-App-Virtual-Makeup using OpenCV

This project is an interactive **virtual makeup editor** built using Python and OpenCV.  
Users can load any image from their device, select a Region of Interest (ROI), create HSV-based masks, apply brightness/darkening effects, preview changes in real time, and save the final edited output — all directly inside OpenCV windows.

---

## 🎥 Demo Video
## [Video](https://youtu.be/D-H5wxNgvyc)

---

## ✨ Features

### 🔹 1. Load image from device  
Uses Tkinter file dialog to import `.jpg`, `.png`, `.jpeg`, `.bmp`, `.tiff`, `.webp`, etc.

### 🔹 2. Mouse-based ROI selection  
- Click and drag to draw a rectangle  
- Cropped region is processed independently  
- Works in **any drag direction** (top→bottom, bottom→top, left→right)

### 🔹 3. Real-time HSV masking  
- Tune **H / S / V min-max** values using trackbars  
- Mask is cleaned with morphological opening & closing  
- Only the masked area is modified

### 🔹 4. Makeup adjustments  
Two enhancement modes:
- **Face mode (`f`)** → Increase brightness  
- **Lips mode (`l`)** → Decrease brightness (darken)  
- Editable via trackbars  
- Real-time preview

### 🔹 5. Save, compare, reset  
- **`s`** → Save edited image  
- **`d`** → Display Before/After comparison  
- **`b`** → Save Before/After combined output  
- **`r`** → Reset mask, trackbars, ROI, and windows  
- On-screen **“Saved!”** message displayed when saving

---

## 🧠 Concepts Used

- OpenCV mouse callbacks (`EVENT_LBUTTONDOWN`, `EVENT_MOUSEMOVE`, `EVENT_LBUTTONUP`)
- Trackbars for live parameter tuning
- HSV color space masking
- Bitwise operations:
  - `inRange()`
  - `bitwise_and()`
- Morphological operations:
  - `MORPH_CLOSE`
  - `MORPH_OPEN`
- Numpy slicing & ROI extraction
- On-image text rendering (`putText`)
- Tkinter file selection

---

## 🛠️ Dependencies

```bash
pip install opencv-python numpy
````

Tkinter comes built-in with most Python distributions.

---

## ▶️ How to Run

```bash
python makeup_editor.py
```

The interface will open automatically.

---

## 🎮 Controls & Keyboard Shortcuts

| Key   | Action                                       |
| ----- | -------------------------------------------- |
| **f** | Face mode (increase brightness)              |
| **l** | Lips mode (darken region)                    |
| **a** | Apply current edits permanently              |
| **s** | Save final result (shows “Saved!” on screen) |
| **d** | Display Before/After comparison              |
| **b** | Save Before/After combined output            |
| **r** | Reset crop, trackbars, mask, preview windows |
| **q** | Quit application                             |

---

## 📂 Project Structure

```
.
├── makeup_editor.py
├── Beautified/
│   ├── makeup_result.jpg
│   ├── before_after.jpg
└── README.md
```

---

## 🧩 Future Enhancements (Optional Ideas)

* Automatic face/lips detection using MediaPipe or Haar Cascades
* Lip color presets (red, pink, nude, maroon)
* Skin smoothing using bilateral/Gaussian filtering
* Full Tkinter GUI (buttons, sliders, live preview)
* Undo/redo feature
* Makeup brushes with freehand drawing
  
