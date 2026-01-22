# Yawn Detector and Counter

![Python](https://img.shields.io/badge/Language-Python-blue)

A real-time computer vision application that detects when a subject is yawning and counts the number of yawns in a session. This project utilizes facial landmarks detection to monitor the mouth's aspect ratio.

## 📋 Table of Contents
- [Description](#description)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [How it Works](#how-it-works)

## 📝 Description
The **Yawn Detector and Counting** system is a computer vision application designed to monitor user fatigue by detecting yawns in real-time. Drowsiness and fatigue are significant factors in accidents and decreased productivity, makes automated monitoring systems crucial for safety and efficiency.

Measurement of yawning frequency is a reliable physiological indicator of drowsiness. This project leverages **Dlib's 68 facial landmark predictor** to map the facial geometry and specifically target the mouth region. By continuously calculating the vertical distance (aspect ratio) between the upper and lower lips, the algorithm identifies when the mouth opens beyond a specific threshold, characterizing a yawn.

**Key capabilities include:**
- **Precision Tracking**: Uses robust facial landmark detection to maintain accuracy even with slight head movements.
- **Session Monitoring**: Maintains a running count of yawns during an active session to quantify fatigue levels over time.
- **Non-intrusive**: Works with standard webcams without requiring specialized hardware.

## ✨ Features
- **Real-time Detection**: Processes video feed from the webcam instantly.
- **Yawn Counting**: Tracks the total number of yawns in the current session.
- **Visual Feedback**: Displays "Subject is Yawning" and the current yawn count directly on the video feed.
- **Landmark Visualization**: Shows the 68 facial landmarks on the face for debugging and visualization.

## 🛠 Tech Stack
- **Python**: Primary programming language.
- **OpenCV**: Used for video capture and image processing.
- **Dlib**: Used for face detection and facial landmark prediction.
- **NumPy**: Used for numerical operations and array manipluation.

## ⚙ Prerequisites
Before running the project, ensure you have the following installed:
- Python 3.6+
- A working webcam

You will also need the Dlib shape predictor model file:
- `shape_predictor_68_face_landmarks.dat` (This should be present in the project directory)

## 📦 Installation

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/Arnab-Ghosh7/Yawn_Detector.git
    cd Yawn_Detector
    ```

2.  **Install Dependencies**
    It is recommended to use a virtual environment.
    ```bash
    pip install opencv-python dlib numpy
    ```
    *Note: Installing `dlib` might require CMake to be installed on your system.*

3.  **Verify Model File**
    Ensure that the `shape_predictor_68_face_landmarks.dat` file is located in the root of the project directory.

## 🚀 Usage

1.  Open the Jupyter Notebook:
    ```bash
    jupyter notebook "Yawn Detector and Counting.ipynb"
    ```

2.  Run the cells in the notebook. Validating the last cell will start the webcam feed.

3.  **Interacting with the App**:
    - The window `Yawn Detection` shows the main feed with status overlays.
    - The window `Live Landmarks` shows the raw facial landmarks.
    - **To Stop**: Press the `Enter` key (Code 13) to close the windows and release the camera.

## 🧠 How it Works
1.  **Face Detection**: Dlib's frontal face detector finds faces in the frame.
2.  **Landmark Extraction**: The shape predictor identifies 68 specific points on the face.
3.  **Lip Analysis**:
    - **Top Lip**: Landmarks 50-52 and 61-63.
    - **Bottom Lip**: Landmarks 65-67 and 56-58.
4.  **Distance Calculation**: The vertical distance between the center of the top and bottom lips is calculated.
5.  **Thresholding**: If the distance exceeds a threshold (currently set to **25**), the system flags a yawn.
6.  **Counting Logic**: A counter increments only when the status changes from "Not Yawning" to "Yawning" to avoid multiple counts for a single yawn event.

---
# Author
Arnab Ghosh
