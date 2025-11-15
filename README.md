# 🐍 Nokia Snake Game — Gesture Controlled
**Python • OpenCV • MediaPipe • Pygame**  
**License:** MIT

A modern, AI-powered twist on the classic Nokia Snake game — fully controlled through **hand gestures** using **MediaPipe**, **OpenCV**, and a **webcam**.

---

## ✨ Overview
This project reimagines the nostalgic Nokia Snake game with real-time gesture control. Using MediaPipe’s advanced hand-tracking pipeline, players control the snake through directional swipes and a pinch-based speed boost, creating an immersive, touch-free gaming experience.

---

## 🎮 Features

### 🐍 Classic Nokia Snake Experience
- Authentic Nokia-style monochrome green theme
- Grid-based movement with smooth animations
- Snake grows after eating fruit
- Full collision detection (walls + self)
- Particle effects for visual feedback
- Score tracking and game-over screen

### 👋 AI-Powered Gesture Controls
- Real-time hand tracking via **MediaPipe Hands**
- Direction control using **swipe gestures**:
  - Swipe Up → Move Up
  - Swipe Down → Move Down
  - Swipe Left → Move Left
  - Swipe Right → Move Right
- **Pinch Gesture** (thumb + index) → Speed Boost
- Built-in **face detection** for gesture window display
- Visual landmark rendering + direction preview

### 🪟 Dual Window Interface
- **Game Window:** Nokia Snake gameplay
- **Gesture Window:** Live camera feed + gesture visualization

---

## 🚀 Quick Start

### 1. Install Dependencies
Run the setup script:
```bash
python setup.py
```

Or install manually:
```bash
pip install -r requirements.txt
```

### 2. Run the Game
```bash
python main.py
```

---

## 📦 Requirements
- Python **3.7+**
- Webcam (internal or external)
- Dependencies:
  - opencv-python ≥ 4.8.0
  - mediapipe ≥ 0.10.0
  - numpy ≥ 1.24.0
  - pygame ≥ 2.4.0

---

## 🎮 Controls

### Hand Gesture Controls
| Gesture | Action |
|--------|---------|
| Swipe Up | Move snake up |
| Swipe Down | Move snake down |
| Swipe Left | Move snake left |
| Swipe Right | Move snake right |
| Pinch (thumb + index) | Speed boost |

### Keyboard Controls
- **ESC** → Quit
- **Q (in gesture window)** → Quit
- **Show UP swipe gesture** → Restart game after Game Over

---

## 🧠 Game Mechanics

### Snake Behavior
- Continuous forward movement
- No immediate reverse direction allowed
- Normal speed & boosted speed
- Growth per fruit eaten

### Scoring
- **+10 points** per fruit
- Running score shown on screen
- Final score shown on Game Over screen

### Game Over Conditions
- Collision with wall
- Collision with self
- Restart via UP gesture

---

## 🗂️ File Structure
```
snake_game/
├── main.py                 # Main game script
├── snake_game.py           # Nokia Snake game logic
├── gesture_controller.py   # Hand gesture detection module
├── setup.py                # Dependency installer
├── requirements.txt        # List of dependencies
└── README.md               # Project documentation
```

---

## ⚙️ Technical Details

### Game Engine
- Built with **Pygame**
- 20×20 pixel grid-based movement
- 60 FPS display
- Dynamic game speed (8–15 FPS)

### Computer Vision
- MediaPipe Hands for accurate hand-landmark detection
- MediaPipe Face Detection
- Real-time gesture recognition via OpenCV
- Movement thresholds for gesture classification

### Architecture
- Threaded execution (game loop + gesture detection)
- Modular classes for clean code separation
- Event-driven gesture interaction

---

## 🛠️ Troubleshooting

### Camera Not Opening
- Ensure no other app is using the webcam
- Change camera index (0 → 1 or 2)
- Check OS-level camera permissions

### Installation Errors
- Upgrade pip:
  ```bash
  python -m pip install --upgrade pip
  ```
- Install dependencies one-by-one if needed
- Use a virtual environment to avoid conflicts

### Performance Issues
- Close other apps using the camera
- Improve lighting for better gesture detection
- Reduce resolution in `snake_game.py` if FPS drops

---

## 🔧 Customization

### Gesture Sensitivity
In `gesture_controller.py`:
```python
self.gesture_threshold = 0.05
```
Lower value → more sensitive.

### Game Speed
In `snake_game.py`:
```python
self.base_speed = 8
self.boost_speed = 15
```

### Colors
Modify in `snake_game.py`:
```python
self.NOKIA_GREEN = (155, 188, 15)
self.LIGHT_GREEN = (204, 255, 51)
```

---

## 🧩 Development Notes

### Adding New Gestures
- Extend `detect_gestures()` in `gesture_controller.py`
- Implement gesture logic using MediaPipe landmarks
- Return new gesture codes
- Handle them in `main.py`

### Modifying Game Mechanics
- Update logic within `SnakeGame` class
- Adjust collision rules, movement, scoring, etc.
- Modify rendering functions to reflect visual changes

---

## 📄 License
This project is licensed under the **MIT License**.

---

## 👤 Author
**Created by: Pranav Gaikwad**  
GitHub: **https://github.com/pranavgaikwad51**

A developer passionate about building innovative AI-enhanced gaming experiences using computer vision and real-time interaction.

---
