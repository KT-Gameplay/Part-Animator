# Part Animator

**Part Animator** is a lightweight, browser-based 2D cutout and symbol animation tool inspired by Adobe Animate (Flash). Designed for creating skeletal/part-based character animations, it supports nested Symbols (**Graphics** and **Movie Clips**), keyframe tweening, onion skinning, project saving, and direct export to **Adobe Animate / BetterTextureAtlas (BTA)** spritemap formats.

---

## 🚀 Getting Started

Part Animator runs entirely in your web browser with no installation or build steps required.
1. Click **＋ Import** in the top bar to load transparent `.png`, `.webp`, or `.jpeg` images (e.g., character body parts like head, torso, arms, and legs).
2. Imported images automatically become reusable **Graphic Symbols** in your Library and are placed onto the center of the stage ($1280 \times 720$).

---

## 🖥️ Workspace Overview

The interface is divided into four main panels:

### 1. Top Header Bar
* **＋ Import:** Load image files from your device into the Library and Stage.
* **＋ New Symbol:** Quickly create a new **Movie Clip** symbol (wraps the currently selected layer if one is active).
* **Export:** Generates a packed texture atlas and animation data compatible with Adobe Animate / BetterTextureAtlas (`spritemap1.png`, `spritemap1.json`, and `Animation.json`).
* **Save Project / Open Project:** Save your entire workspace—including embedded image data, symbols, layers, and keyframes—as a `.partanim` file to resume editing later.
* **New:** Clears the current workspace to start fresh.

### 2. Left Panel: Layers & Library
Switch between the **Layers** and **Library** tabs at the top of the panel:
* **Layers Tab:**
  * Manage the stacking order and visibility (`◉` / `○`) of parts in the active scene or symbol.
  * Use **＋ Add**, **Duplicate**, or **Delete** to manage layers.
  * Icons indicate layer types: `▣` for Symbol instances, `▧` for raw bitmaps.
* **Library Tab:**
  * Stores all imported Graphic symbols and custom Movie Clips.
  * **Add to Stage:** Drag and drop any library item directly onto the stage canvas, or select it and click **Add to Stage**.
  * **Edit Symbol:** Double-click a symbol in the Library (or select it and click **Edit**) to enter its internal timeline.

### 3. Center Panel: Stage & Viewport
* **Direct Manipulation:** Click and drag on the canvas to move the currently selected layer.
* **Fit:** Resets zoom and centers the $1280 \times 720$ stage inside your viewport.
* **Center:** Snaps the selected layer to the exact center of the stage ($640, 360$).
* **Onion: On/Off:** Toggles onion skinning, displaying a semi-transparent ghost of the previous frame to help align smooth motion.
* **← Scene:** Appears when editing inside a Symbol; click it to return to the main Stage timeline.

### 4. Right Panel: Properties
Adjust transform values for the selected layer at the current frame. Changing any slider automatically creates or updates a keyframe on the current frame:
* **X / Y:** Position coordinates on the stage.
* **Rotation:** Angle in degrees ($-360^\circ$ to $360^\circ$).
* **Scale X / Scale Y:** Horizontal and vertical scaling ($0.05\times$ to $5.00\times$).
* **Opacity:** Transparency ($0.00$ to $1.00$).
* **Name:** Rename the selected layer.

### 5. Bottom Panel: Timeline & Playback
* **Playback Controls:** Play/Pause (`▶ Play`), Stop and return to Frame 1 (`■`), or step backward/forward one frame (`◀` / `▶`).
* **◆ Keyframe:** Manually inserts a keyframe (`◆`) on the active layer at the current playhead frame.
* **Frame / FPS:** Jump directly to a specific frame number or adjust playback speed (1–60 FPS, default `24`).
* **Scrubbing:** Click any frame number in the top ruler or any cell in a layer track to move the playhead.

---

## 🎬 Animation Workflow

### Keyframing & Tweening
Part Animator uses linear interpolation between keyframes:
1. Select a layer in the **Layers** panel.
2. Move the playhead to **Frame 1** and position your part on the stage.
3. Click another frame on the timeline (e.g., **Frame 15**).
4. Drag the part on the stage or adjust its **Properties** sliders. A new orange diamond keyframe (`◆`) will appear, and the frames in between will automatically animate smoothly.

### Working with Symbols (Graphics vs. Movie Clips)
Just like Adobe Animate, Part Animator distinguishes between two symbol types:
* **Graphic (`▣`):** Static or single-frame reusable artwork. Every imported image is automatically wrapped in a Graphic symbol.
* **Movie Clip (`🎞`):** Independent, looping mini-timelines (default 24 frames). Great for cyclical animations like blinking eyes, wagging tails, or spinning wheels.
  1. Select a part on the stage (optional) and click **＋ Movie Clip** in the Library tab.
  2. You will automatically enter **Symbol Edit Mode** (indicated in the top toolbar).
  3. Animate the parts inside the Movie Clip's own timeline.
  4. Click **← Scene** above the stage to return to the main timeline. When you play the main timeline, your Movie Clip will loop automatically!

---

## 📦 Exporting & File Formats

### Saving Your Work (`.partanim`)
* Click **Save Project** to download `PartAnimator-Project.partanim`.
* Because all imported images are encoded directly inside the file, you can share this single file or reload it anytime via **Open Project** without losing your assets.

### Exporting for Game Engines / Adobe Animate
Clicking **Export** packs all imported bitmaps into a single sprite sheet and downloads three files compatible with **BetterTextureAtlas (BTA)** and **Adobe Animate** workflows:
1. `spritemap1.png`
2. `spritemap1.json`
3. `Animation.json`
