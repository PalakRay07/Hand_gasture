# 🖐️ Hand Gesture Controller  
### MediaPipe + OpenCV | Computer Vision | Human–Computer Interaction

<p align="center">

<img src="https://img.shields.io/badge/Python-3.9--3.11-blue?style=for-the-badge&logo=python" />
<img src="https://img.shields.io/badge/OpenCV-Computer%20Vision-red?style=for-the-badge&logo=opencv" />
<img src="https://img.shields.io/badge/MediaPipe-Hands-green?style=for-the-badge&logo=google" />
<img src="https://img.shields.io/badge/Platform-Windows%2010%2F11-lightgrey?style=for-the-badge&logo=windows" />
<img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" />
<img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" />

</p>

---

## 🚀 Project Overview

A real-time webcam-based **Gesture Control System** that translates human hand gestures into OS-level actions such as:

- 🖱️ Mouse movement & clicking  
- ✊ Drag-and-drop  
- 📜 Vertical & horizontal scrolling  
- 🔊 System volume control  
- 💡 Screen brightness adjustment  

Built using **MediaPipe Hands** and **OpenCV**, this project demonstrates practical computer vision applied to real-world human-computer interaction systems.

---

## 📊 Project Highlights

<p align="center">
<img src="https://img.shields.io/badge/Real--Time-Low%20Latency-blueviolet?style=flat-square" />
<img src="https://img.shields.io/badge/21-Landmarks%20Per%20Hand-orange?style=flat-square" />
<img src="https://img.shields.io/badge/8-Gesture%20Types-success?style=flat-square" />
<img src="https://img.shields.io/badge/Automation-PyAutoGUI-informational?style=flat-square" />
</p>

### 🎯 Key Features

- Real-time hand landmark detection (21 points per hand)
- Cursor smoothing to reduce jitter
- Gesture-based left, right & double click
- Click-and-drag via fist gesture
- Vertical & horizontal scrolling
- System volume control (Windows via PyCAW)
- Screen brightness adjustment
- Low-latency interaction pipeline

---

# 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Computer Vision | MediaPipe Hands |
| Image Processing | OpenCV |
| Automation | PyAutoGUI |
| Volume Control | PyCAW + COM |
| Brightness Control | screen-brightness-control |
| Language | Python (3.9–3.11) |

---

# 📦 System Requirements

- **OS:** Windows 10 / 11 (recommended)
- **Hardware:** Integrated or external webcam
- **Python:** 3.9 – 3.11
- Good lighting for accurate tracking

---

# ⚙️ Installation Guide

## 1️⃣ Create Virtual Environment (Recommended)

```python -m venv .venv.\.venv\Scripts\Activate.ps1```

## 2️⃣ Install Dependencies

If requirements.txt exists:

```pip install -r requirements.txt```

If not, create requirements.txt:

```python
 opencv-python>=4.8.0
mediapipe>=0.10.11
numpy>=1.23
pyautogui>=0.9.54
pycaw>=20230407
comtypes>=1.2.0
screen-brightness-control>=0.22.2
protobuf>=3.20.3,<5
```

Then install:

```pip install -r requirements.txt```

### 📥 Getting the Code

Clone Repository
```python
git clone https://github.com/PalakRay07/Hand_gasture.git
cd Hand_gasture
```

Or download ZIP and extract.

Ensure ```Code.py``` is in the root directory.

▶️ Run the Application

```python Code.py```

A window titled "Gesture Controller" will open showing:

Webcam feed

Hand landmarks

Real-time gesture detection

Press Enter to exit.

### 🧠 Architecture Overview

### 1️⃣ MediaPipe Layer

Detects 21 hand landmarks

Identifies hand orientation (Right / Left)

### 2️⃣ Gesture Recognition Module

Custom ```HandRecog``` logic:

Detects open/closed fingers

### Encodes gestures:

```- PALM```

```- FIST```

```- INDEX```

```- MID```

```- TWO_FINGER_CLOSED```

```- V_GEST```

```- PINCH_MAJOR```

```- PINCH_MINOR```

### 3️⃣ Gesture Controller

Routes gestures to OS controller

Applies smoothing algorithm

### 4️⃣ OS Interaction Layer

pyautogui → Mouse control

pycaw → Volume adjustment

screen_brightness_control → Brightness control

✋ Gesture → Action Mapping
Gesture	Action
✌️ V_GEST	Enable pointer movement
✊ FIST	Click-and-drag
🖕 MID	Left click
☝️ INDEX	Right click
🤏 TWO_FINGER_CLOSED	Double click
🤏 PINCH_MINOR	Scroll
🤏 PINCH_MAJOR	Volume / Brightness

### Pinch Motion Controls

- Vertical motion → Volume or vertical scroll

- Horizontal motion → Brightness or horizontal scroll

### 🎯 Optimization Techniques

- Pointer smoothing to reduce jitter

- Gesture hold validation to prevent accidental clicks

- Dominant-hand detection

- Threshold-based pinch recognition

### 🧪 Troubleshooting

### ❌ Blank Window

Ensure webcam is connected

Try changing:

```cv2.VideoCapture(0)```

to 1 or 2.

### ❌ Unstable Gestures

Improve lighting

Keep hand fully visible

Avoid fast movements

### ❌ Volume / Brightness Not Working

Ensure Windows audio endpoint support

Enable DDC/CI for external monitors

### 🔒 Safety Notice

```pyautogui.FAILSAFE = False``` is enabled.
Keep the app window focused to exit safely by pressing Enter.

Only run trusted source code and review ```Code.py``` before execution.

### 🌟 Future Improvements

- Gesture calibration mode

- Customizable gesture mapping

- GUI control dashboard

- macOS / Linux support

- ML-based dynamic gesture learning

- IoT device integration

### 👩‍💻 Author

Palak.
Computer Engineering Student | AI & Computer Vision Enthusiast

📧 palak070704@gmail.com

🔗 https://github.com/PalakRay07

💡 Why This Project Matters

This project demonstrates:

Real-time computer vision engineering

Human–computer interaction design

OS-level automation

Signal smoothing & gesture stability

Practical ML integration
