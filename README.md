# Smart Home Automation System using YOLOv8 

A Python-based Smart Home Controller that uses computer vision to monitor room occupancy and manage energy usage. This project leverages a YOLOv8 model to detect people via a webcam feed and provides a simple Tkinter GUI for user control and alerts.

Features

- **Real-Time Person Detection**: Uses YOLOv8 (Nano) to detect occupants in a room.
- **Device Status Monitoring**: Simulates smart devices (lights, fans, electronics) with real-time status updates.
- **Energy Saving Alerts**: Warns the user if devices are ON and no person is detected to minimize energy waste.
- **User-Friendly Interface**: Intuitive GUI built with Tkinter.

## Installation

### Prerequisites

- Python 3.7+
- [YOLOv8 model weights](https://docs.ultralytics.com/models/)
- A working webcam

### Required Python Packages

Install dependencies using pip:

```
pip install ultralytics opencv-python-headless pillow
```
*For some systems, you may need `opencv-python` instead of `opencv-python-headless`.*

## Model Setup

- The application uses the YOLOv8 Nano model for efficiency.
- Download the model file (`yolov8n.pt`) from [Ultralytics](https://github.com/ultralytics/ultralytics) if not already present.
- Place `yolov8n.pt` in your working directory (or adjust the model path in the code).

## Usage

1. **Clone the repository** and navigate to the project directory.
2. **Run the main application:**

   ```sh
   python smart_home_system.py
   ```

3. **UI Controls:**
   - Click "Start Camera" to begin live room monitoring.
   - Click "Stop Camera" to halt monitoring.
   - Use "Emergency Stop" to terminate the app immediately.

4. **System Behavior:**
   - When a person is detected, the status updates to indicate normal operation.
   - When the room is empty and devices are ON, an alert is shown to remind the user to turn them off.

## Code Overview

**Main Components:**
- `SmartHomeSystem` class: Handles the GUI and core logic.
- `monitor_room()`: Processes frames from webcam and runs person detection.
- `check_energy_waste()`: Checks if any simulated device is unnecessarily ON and alerts the user.
- Device states are simulated in software (you can expand for hardware integration).

## Customization

- **Adjust the device simulation** in `self.devices` (e.g., add more types of appliances).
- **Change the timeout** with the `auto_shutdown` variable.
- **Modify detection code** to perform real device actions (e.g., with GPIO, relay controls for Raspberry Pi, or IoT APIs).

## Limitations & Future Work

- Current version uses simulated devices. Real-world deployment needs hardware integration.
- Alerts are via pop-up; can be extended to SMS, email, or smart home notifications.
- Only differentiates person/not-person; can extend for specific users or pets.
- Security, remote access, and voice control are possible future enhancements.


## Credits

- [Ultralytics YOLO](https://ultralytics.com/)
- [OpenCV](https://opencv.org/)
- [Tkinter](https://docs.python.org/3/library/tkinter.html)

