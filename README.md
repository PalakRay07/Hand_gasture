🖐️ Hand Gesture Controller
MediaPipe + OpenCV | Computer Vision | Human-Computer Interaction

A real-time webcam-based gesture control system that translates hand gestures into OS-level actions such as mouse movement, clicking, scrolling, system volume control, and screen brightness adjustment.

Built using MediaPipe Hands and OpenCV, this project demonstrates practical computer vision applied to real-world interaction systems.

🚀 Key Highlights

🎯 Real-time hand landmark detection (21 points per hand)

🖱️ Cursor movement with smoothing (jitter reduction)

👆 Gesture-based clicking (left, right, double)

✊ Drag-and-drop support

📜 Vertical & horizontal scrolling

🔊 System volume control (Windows via PyCAW)

💡 Screen brightness adjustment

⚡ Low-latency interaction

🛠️ Tech Stack
Category	Technology
Computer Vision	MediaPipe Hands
Image Processing	OpenCV
Automation	PyAutoGUI
Volume Control	PyCAW + COM
Brightness Control	screen-brightness-control
Language	Python (3.9–3.11 recommended)
📦 System Requirements

OS: Windows 10 / 11 (recommended)

Hardware: Integrated or external webcam

Python: 3.9 – 3.11

Good lighting environment for accurate tracking

⚙️ Installation Guide
1️⃣ Create Virtual Environment (Recommended)
python -m venv .venv
.\.venv\Scripts\Activate.ps1
2️⃣ Install Dependencies

If requirements.txt exists:

pip install -r requirements.txt

If not, create one with:

opencv-python>=4.8.0
mediapipe>=0.10.11
numpy>=1.23
pyautogui>=0.9.54
pycaw>=20230407
comtypes>=1.2.0
screen-brightness-control>=0.22.2
protobuf>=3.20.3,<5

Then run:

pip install -r requirements.txt
📥 Getting the Code
Option A – Clone Repository
git clone https://github.com/PalakRay07/Hand_gasture.git
cd Hand_gasture
Option B – Download ZIP

Download from GitHub and extract.

Ensure Code.py exists in the root directory.

▶️ Running the Application
python Code.py

A window titled “Gesture Controller” will open displaying:

Webcam feed

Hand landmarks

Real-time gesture recognition

Press Enter to exit.

🧠 How It Works (Architecture Overview)
1️⃣ MediaPipe Hands

Detects 21 landmarks per hand

Identifies hand orientation (Right / Left)

2️⃣ Gesture Recognition Layer

Custom HandRecog module:

Detects open/closed fingers

Encodes gestures:

PALM

FIST

INDEX

MID

TWO_FINGER_CLOSED

V_GEST

PINCH_MAJOR

PINCH_MINOR

3️⃣ Gesture Controller

Routes detected gestures to OS controller

Applies smoothing for stable pointer movement

4️⃣ OS Interaction Layer

pyautogui → Mouse actions

pycaw → System volume

screen_brightness_control → Brightness

✋ Gesture → Action Mapping
Gesture	Action
✌️ V_GEST	Enable pointer movement
✊ FIST	Click-and-drag
🖕 MID	Left click
☝️ INDEX	Right click
🤏 TWO_FINGER_CLOSED	Double click
🤏 PINCH_MINOR	Scroll
🤏 PINCH_MAJOR	Volume / Brightness
Pinch Controls

Vertical motion → Volume or vertical scroll

Horizontal motion → Brightness or horizontal scroll

🎯 Optimization Techniques Used

Pointer movement smoothing to reduce jitter

Gesture hold validation to avoid accidental clicks

Dominant-hand detection

Threshold-based pinch detection

📷 Suggested Screenshots Section (Add Later)

Create an images folder and add:

## Demo

![Tracking](images/tracking.png)
![Pinch](images/pinch.png)
![Volume Control](images/volume.png)
🧪 Troubleshooting
❌ Blank or closing window

Check webcam connection

Change camera index in:

cv2.VideoCapture(0)

Try 1 or 2 instead.

❌ Erratic Gesture Detection

Improve lighting

Keep hand fully visible

Avoid fast movements

Reduce background clutter

❌ Volume / Brightness Not Working

Volume requires Windows audio endpoint

External monitors may not support brightness control

Enable DDC/CI for external displays

🔒 Safety Notes

pyautogui.FAILSAFE = False is enabled
→ Keep app window focused to exit safely.

Only run trusted source code.

Review Code.py before executing.

🌟 Future Improvements

Add gesture calibration mode

Add GUI control panel

Add gesture customization

Add macOS / Linux support

Add ML-based dynamic gesture learning

Integrate with IoT smart devices

👩‍💻 Author

Palak Ray
Computer Engineering Student | AI & Computer Vision Enthusiast

📧 palak070704@gmail.com

🔗 https://github.com/PalakRay07

💡 Why This Project Matters

This project demonstrates:

Real-time computer vision

Human-computer interaction design

OS-level automation

Signal smoothing & gesture stability

Practical ML integration

It’s not just a demo — it’s a functional alternative input system.
