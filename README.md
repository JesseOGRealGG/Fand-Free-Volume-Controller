<img width="1170" height="856" alt="Screenshot 2026-06-08 170514" src="https://github.com/user-attachments/assets/63ff5dd0-c813-4313-96cd-818ff1ce31b9" /><img width="1172" height="844" alt="Screenshot 2026-06-08 170359" src="https://github.com/user-attachments/assets/01cd81ad-d221-4d82-abf4-c9ff49bfda9c" />

# Hand Gesture Volume Control

A Python-based computer vision project that allows users to control their system volume using **hand gestures** through a webcam. The application uses **MediaPipe Hand Tracking** to detect finger landmarks and adjusts the computer's master volume based on the distance between the **thumb and index finger**.

---

## Features

*  **Real-time hand tracking** using a webcam
*  **Gesture-based volume control**
*  Dynamically adjusts **system audio volume**
*  Real-time visual feedback with an on-screen volume bar
*  Custom sensitivity adjustment through a simple **Tkinter settings window**
*  Smooth and responsive webcam interface powered by OpenCV

---

## How It Works

The project uses a webcam feed to detect and track a user's hand in real time.

1. **Hand Detection**
   The application uses **MediaPipe Hands** to detect hand landmarks and track finger positions.

2. **Distance Measurement**
   The system calculates the distance between:

   * **Thumb tip (Landmark 4)**
   * **Index finger tip (Landmark 8)**

3. **Volume Mapping**
   The measured distance is multiplied by a user-defined sensitivity value and mapped to the system volume range.

4. **Volume Control**
   Using **Pycaw**, the program updates the Windows master volume dynamically.

5. **Visual Feedback**
   The webcam window displays:

   * Hand landmarks
   * A line between fingers
   * A volume progress bar
   * Current volume percentage

---

## File Structure

```bash
project-folder/
│── main.py              # Main application script
│── requirements.txt     # Required Python dependencies
│── README.md            # Project documentation
```

### Main Components

#### `HandDetector` Class

Responsible for:

* Detecting hands using MediaPipe
* Tracking landmark positions
* Identifying finger states
* Calculating distances between fingers

#### `get_length_multiplier()`

Creates a **Tkinter settings popup** where the user enters a sensitivity multiplier for gesture tracking.

#### `main()`

Controls the main application loop:

* Starts webcam capture
* Detects hand gestures
* Calculates finger distance
* Maps values to system volume
* Displays live visual feedback

---

## Technologies Used

* **Python**
* **OpenCV (`cv2`)** – webcam processing and visualization
* **MediaPipe** – hand tracking and landmark detection
* **Pycaw** – Windows audio control
* **NumPy** – interpolation calculations
* **Tkinter** – GUI settings popup

---

## Installation

Clone the repository:

```bash
git clone <your-repository-url>
cd hand-gesture-volume-control
```

Install dependencies:

```bash
pip install opencv-python mediapipe numpy pycaw comtypes
```

Or install from a requirements file:

```bash
pip install -r requirements.txt
```

---

## How to Run

Run the application using:

```bash
python main.py
```

### Steps

1. Launch the application.
2. Enter a **length multiplier value** (recommended: `3–4`) in the settings popup.
3. Allow webcam access.
4. Move your **thumb and index finger closer or farther apart**:

   * Fingers closer → Lower volume
   * Fingers farther apart → Higher volume

### Controls

* **ESC key** → Exit the application
* **Window close button (X)** → Close safely

---

## Requirements

* **Python 3.8+**
* A working **webcam**
* **Windows OS** (required for Pycaw volume control)

---

## Future Improvements

* Multi-hand support
* Gesture customization
* Brightness control mode
* Cross-platform audio support
* Better gesture smoothing and stability

---

## Demo

You can add screenshots or a GIF here to showcase the project in action.

---

## License

This project is open-source and available under the **MIT License**.
