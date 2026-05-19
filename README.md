# Traffic Violation Detection System

## Project Description

This project is an intelligent traffic violation detection system using YOLOv8 computer vision models. It automatically detects and records traffic violations including red light running by analyzing video feeds from traffic cameras.

The system uses multiple specialized YOLO models to:

- Detect vehicles on the road
- Identify and read license plates (OCR)
- Monitor traffic light status
- Track vehicle movement patterns
- Record violations with evidence images

## Features

- **Vehicle Detection**: Identifies and tracks vehicles in video feeds using YOLOv8m
- **License Plate Detection & OCR**: Detects license plates and extracts plate numbers using specialized YOLO models
- **Traffic Light Monitoring**: Recognizes traffic light colors (red, yellow, green)
- **Red Light Violation Detection**: Identifies vehicles running red lights
- **Violation Recording**: Automatically captures and saves images of violations with timestamps
- **Vehicle Tracking**: Tracks vehicle movement across frames to determine violation patterns

## Project Structure

```
lsb-computer-vision-prj/
├── main.py                          # Main processing script
├── traffic_violation.py              # Traffic violation detection module
├── main_test.py                      # Test script
├── draft_license_plate.py            # Draft: License plate detection
├── draft_traffic_light.py            # Draft: Traffic light detection
├── draft_vehicle.py                  # Draft: Vehicle detection
├── requirements.txt                  # Python dependencies
├── pyproject.toml                    # Project configuration
├── yolov8m.pt                        # YOLOv8m vehicle detection model
├── models/                           # Trained custom models
│   ├── license_plate/
│   │   ├── license_plate_detection.pt # License plate detection model
│   │   └── license_plate_ocr.pt      # License plate OCR model
│   ├── traffic_light/
│   │   └── traffic_light.pt          # Traffic light detection model
│   └── vehicle/
│       └── vehicle.pt                # Vehicle detection model
├── data_test/                        # Test video data
├── violations/                       # Output: Recorded violation images
└── debug_plates/                     # Debug: License plate samples
```

## Models Used

1. **YOLOv8m** (`yolov8m.pt`): General-purpose object detection for vehicles
2. **License Plate Detection** (`license_plate_detection.pt`): Custom model for detecting license plates
3. **License Plate OCR** (`license_plate_ocr.pt`): Custom model for character recognition on plates
4. **Traffic Light Detection** (`traffic_light.pt`): Custom model for traffic light status recognition

## Requirements

- Python >= 3.12
- OpenCV (cv2)
- Ultralytics YOLO
- NumPy

See [requirements.txt](requirements.txt) for complete dependencies.

## Usage

pip install -r requirements.txt

### Video Processing

Process a video file using the main script:

```bash
python main.py
```

### Testing

Run the test suite:

```bash
python main_test.py
```

## Output

Detected violations are saved to the `violations/` directory with:

- Timestamped images showing the violation
- License plate information (if detected)
- Violation type and confidence scores

## Configuration

Key parameters that can be adjusted in the scripts:

- `STOPLINE_Y`: Y-coordinate of the stop line for red light detection
- `RESIZE_WIDTH`: Resolution for frame processing
- `DISPLAY_FRAME`: Enable/disable frame visualization

## License

This project is part of the LSB Computer Vision initiative.
