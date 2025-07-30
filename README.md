# 🧊 Rubik's Cube Solver

This project is a real-time Rubik’s Cube solver that scans cube faces using a webcam, classifies colors with a trained ML model, and solves the cube using the Kociemba algorithm—all via an interactive GUI. It simplifies the solving process, typically completing the cube in ~20 optimal moves.

![Algorithim Block Diagram](<img width="1146" height="369" alt="Image" src="https://github.com/user-attachments/assets/bd7216ee-3feb-4a97-b7a0-556874074fc8" />)

![Function Web Application](<img width="1282" height="749" alt="Image" src="https://github.com/user-attachments/assets/4e1c136e-a82b-4f92-b011-ac8f9b229a22" />)
---

## 🚀 Features

- 🎥 **Live Camera Integration**: Detects the cube and its color tiles in real-time using OpenCV.
- 🎯 **Color Classification**: Uses a trained logistic regression model for RGB-based color classification.
- 🧠 **Solving Algorithm**: Computes efficient cube solutions using the Kociemba algorithm (~20 steps max).
- 🧩 **GUI Interface**: Built with Tkinter for visual scanning, face updates, and animated solving instructions.
- 🔄 **Reset & Replay**: Allows full scan-reset-solve cycles via intuitive buttons.

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

## 📂 Project Structure

rubiks_cube_solver/
├── color_train.py         # Trains logistic regression on RGB color data
├── image_processing.py    # Image capture and grid detection logic
├── main.py                # GUI app and solving flow
├── model.sav              # Pre-trained logistic regression model
├── *.xlsx                 # RGB datasets for each cube face (training data)
├── README.md              # Project documentation
---

## 🛠️ Installation & Usage
  1. Clone the Repository
  bash
  Copy
  Edit
  git clone https://github.com/your-username/rubiks_cube_solver.git
  cd rubiks_cube_solver
  2. Install Dependencies
  bash
  Copy
  Edit
  pip install opencv-python scikit-learn pandas numpy Pillow kociemba
  3. Run the Application
  bash
  Copy
  Edit
  python main.py
  4. (Optional) Retrain the Model
  If you’ve updated or added color data, retrain the color classifier:
  
  bash
  Copy
  Edit
  python color_train.py

## 💡 How It Works

1. Color Model Training: Six .xlsx files contain RGB values for each cube face color. These are used to train a logistic regression model.

2. Face Scanning: The webcam captures cube faces and detects the 3×3 grid layout via contour analysis.

3. Color Classification: Each grid cell’s RGB average is predicted as a color label using the trained ML model.

4.Cube Solving: Once all six faces are scanned, a cube state string is passed to the Kociemba solver for an optimal solution.

5. Step-by-Step GUI Display: The GUI visually displays each move with directional arrows, guiding the user to solve the cube interactively.
