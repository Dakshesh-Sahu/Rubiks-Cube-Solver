# 🧊 Rubik's Cube Solver

This project is a real-time Rubik’s Cube solver that scans cube faces using a webcam, classifies colors with a trained ML model, and solves the cube using the Kociemba algorithm—all via an interactive GUI. It simplifies the solving process, typically completing the cube in ~20 optimal moves.

<img width="1282" height="749" alt="Image" src="https://github.com/user-attachments/assets/b5975628-3be3-4c81-b826-3f12438ade1c" />

![Function Web Application](<img width="1282" height="749" alt="Image" src="https://github.com/user-attachments/assets/4e1c136e-a82b-4f92-b011-ac8f9b229a22" />)
---

## 🚀 Features

- 🎥 **Live Camera Integration**: Detects the cube and its color tiles in real-time using OpenCV.
- 🎯 **Color Classification**: Uses a trained logistic regression model for RGB-based color classification.
- 🧠 **Solving Algorithm**: Computes efficient cube solutions using the Kociemba algorithm (~20 steps max).
- 🧩 **GUI Interface**: Built with Tkinter for visual scanning, face updates, and animated solving instructions.
- 🔄 **Reset & Replay**: Allows full scan-reset-solve cycles via intuitive buttons.
- 
<img width="1146" height="369" alt="Image" src="https://github.com/user-attachments/assets/68ad9ebe-6a60-41f5-8891-683f9f206f76" />

---

## 🧰 Tech Stack

| Tool | Purpose |
|------|---------|
| **Python 3.8+** | Main programming language |
| **OpenCV** | Image processing and contour detection |
| **Scikit-learn** | ML model for color classification |
| **Tkinter + PIL** | GUI rendering and face visualizations |
| **Kociemba** | Solving the cube using 2-phase optimal algorithm |

---

## 💡 How It Works

1. Color Model Training: Six .xlsx files contain RGB values for each cube face color. These are used to train a logistic regression model.

2. Face Scanning: The webcam captures cube faces and detects the 3×3 grid layout via contour analysis.

3. Color Classification: Each grid cell’s RGB average is predicted as a color label using the trained ML model.

4. Cube Solving: Once all six faces are scanned, a cube state string is passed to the Kociemba solver for an optimal solution.

5. Step-by-Step GUI Display: The GUI visually displays each move with directional arrows, guiding the user to solve the cube interactively.
