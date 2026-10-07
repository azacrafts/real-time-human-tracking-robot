# Real-Time Human Tracking Robot

A computer-vision-based robotic system that detects and tracks a person in real time using YOLOv5.

The system processes webcam frames with Python and OpenCV, detects a person using YOLOv5, calculates the target's position relative to the center of the frame, and sends movement commands to an Arduino via serial communication.

The Arduino controls two servo motors to keep the camera aligned with the detected person.

## Features

- Real-time person detection using YOLOv5
- Webcam processing with OpenCV
- Human position tracking
- Target position smoothing
- Python-to-Arduino serial communication
- Two-axis servo control
- Automatic camera alignment
- CAD model of the robotic mechanism

## Technologies

- Python
- OpenCV
- PyTorch
- YOLOv5
- Arduino
- Serial Communication
- Servo Motors

## How It Works

1. A webcam captures video frames.
2. YOLOv5 detects a person in each frame.
3. Python calculates the person's position relative to the center of the image.
4. The position data is sent to the Arduino through a serial connection.
5. The Arduino adjusts two servo motors to move the camera toward the detected person.
6. The process repeats continuously, allowing the system to track the person in real time.

## Installation

Install the required Python dependencies:

```bash
pip install -r requirements.txt
```

## Usage

1. Connect the Arduino, webcam, and servo motors.
2. Upload `robot_controller.ino` to the Arduino.
3. Close the Arduino Serial Monitor before running the Python application.
4. Open `human_tracker.py`.
5. Set `SERIAL_PORT` to the port used by your Arduino.

For example:

```python
SERIAL_PORT = 'COM3'
```

6. Run the tracking application:

```bash
python human_tracker.py
```

Press `q` to stop the application.

## Project Structure

```text
real-time-human-tracking-robot/
├── human_tracker.py
├── robot_controller.ino
├── robot_model.step
├── requirements.txt
└── README.md
```

## CAD Model

The repository includes a STEP model of the robotic mechanism:

`robot_model.step`

## Future Improvements

- Improve tracking stability
- Add automatic serial port detection
- Improve servo movement smoothing
- Add a graphical interface for configuration