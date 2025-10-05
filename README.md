# Hand Gesture Controller (MediaPipe + OpenCV)

A webcam-based hand gesture controller that uses MediaPipe to detect hand landmarks and maps gestures to OS actions: mouse movement, clicks, scrolling, system volume, and screen brightness.


## Features
- Real-time hand tracking with MediaPipe Hands.
- Gesture recognition for common interactions.
- Cursor control with movement smoothing to reduce jitter.
- Click, right-click, double-click, and click-and-drag via gestures.
- Scroll vertically or horizontally using a pinch gesture.
- Adjust system volume and display brightness using pinch gestures.

## Requirements
- OS: Windows 10/11 recommended (system volume control uses PyCAW/COM).
- Hardware: Integrated or external webcam.
- Python: 3.9–3.11 recommended.

## Install
1) Create and activate a virtual environment (Windows PowerShell):
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2) Install dependencies:
```powershell
pip install -r requirements.txt
```
If you don’t have the file locally yet, create `requirements.txt` with the following content:
```txt
opencv-python>=4.8.0
mediapipe>=0.10.11
numpy>=1.23
pyautogui>=0.9.54
pycaw>=20230407
comtypes>=1.2.0
screen-brightness-control>=0.22.2
protobuf>=3.20.3,<5
```

## Getting the Code
- Option A: Clone the original repo
```powershell
git clone https://github.com/PalakRay07/Hand_gasture.git
```
- Option B: Download ZIP from GitHub and extract.

Ensure `Code.py` is present in your working directory.

## Run
From the project directory (with the venv activated):
```powershell
python Code.py
```
A window titled "Gesture Controller" will open showing your webcam feed with hand landmarks. Press Enter to exit.

## How It Works (High Level)
- `MediaPipe Hands` detects 21 landmarks per hand per frame.
- `HandRecog` infers which fingers are open/closed and recognizes higher-level gestures:
  - Encoded gestures like `PALM`, `FIST`, `INDEX`, `MID`, `TWO_FINGER_CLOSED`, `V_GEST`, `PINCH_MAJOR`, `PINCH_MINOR`.
- `GestureController` reads frames, routes recognized gestures to `Controller`.
- `Controller` performs OS actions with `pyautogui`, brightness via `screen_brightness_control`, and volume via `pycaw`.

## Gesture → Action Mapping
- V sign (`V_GEST`): Enable pointer movement (cursor follows your hand).
- Fist (`FIST`): Click-and-drag while moving (mouse down held).
- Middle finger open (`MID`) with movement flag: Left click.
- Index only (`INDEX`) with movement flag: Right click.
- Two fingers closed (`TWO_FINGER_CLOSED`) with movement flag: Double click.
- Pinch minor (usually left hand, `PINCH_MINOR`): Scroll.
  - Vertical pinch motion → vertical scroll.
  - Horizontal pinch motion → horizontal scroll (Shift+Ctrl+Scroll).
- Pinch major (usually right hand, `PINCH_MAJOR`): System controls.
  - Horizontal pinch → screen brightness.
  - Vertical pinch → system volume.

Notes:
- “Movement flag” is set when `V_GEST` enables pointer movement; some click gestures only register when this flag is set to reduce accidental clicks.
- Handedness (major/minor) is determined by MediaPipe labels (Right/Left) and a dominant-hand flag.

## Tips for Reliable Use
- Good, even lighting; avoid strong backlight.
- Keep the hand inside the camera frame; use clear, deliberate gestures.
- Sit at a consistent distance from the camera.
- Start with open palm, then switch to desired gesture.

## Troubleshooting
- App window is blank or closes immediately:
  - Ensure a webcam is connected and not used by another program.
  - Try switching to a different camera index in `cv2.VideoCapture(0)` (e.g., 1, 2).

- Gestures are not recognized or erratic:
  - Improve lighting and reduce background clutter.
  - Keep the hand closer to the camera and fully visible.
  - Avoid very fast motions; maintain gestures for a brief moment.

- Volume/brightness not changing (Windows):
  - Volume requires PyCAW and Windows audio endpoint support.
  - Brightness control depends on your display/driver. External monitors may need DDC/CI enabled or might not support software control.

- Cursor moves uncontrollably:
  - The code sets `pyautogui.FAILSAFE = False`. Move slowly and press Enter in the app window to exit.

## Security and Safety
- Disabling PyAutoGUI failsafe means you cannot abort by slamming the mouse to the top-left. Keep the app window focused so Enter can exit.
- Only run downloaded code you trust. Review `Code.py` before executing.

## Project Structure (original repo)
- `Code.py` — main implementation.
- `Report And Summary.pdf` — writeup.
- `Video of the working of the project.mp4` — demo video.

## Acknowledgements
- MediaPipe Hands by Google.
- OpenCV for video processing.
- PyAutoGUI for input automation.
- PyCAW for Windows audio control.
- screen-brightness-control for display brightness adjustments.
