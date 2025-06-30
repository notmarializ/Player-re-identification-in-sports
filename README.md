# Player-re-identification-in-sports
Player re-identification in sports footage


# ⚽ Player Tracking with YOLO + ByteTrack + ReID

This project performs multi-object tracking of football players, referees, and the ball in a video using a combination of:
- **YOLO (Ultralytics)** for object detection
- **ByteTrack** for object tracking
- **Re-ID (ResNet18)** for consistent player identification across frames (even when temporarily occluded)


## 🚀 Features

- ⚡ **Fast and accurate detection** using YOLOv8.
- 📌 **ByteTrack** for tracking objects across frames.
- 🧠 **Re-Identification (ReID)** using a ResNet18 backbone to assign persistent IDs.
- 🎥 **Video I/O support** with OpenCV.
- 🧩 Handles identity switches and occlusions by comparing feature embeddings.
- 🎨 Annotated output video with bounding boxes and consistent IDs.

---

## 🔧 Installation

### 1. Clone and install ByteTrack:
```bash
git clone https://github.com/ifzhang/ByteTrack.git
cd ByteTrack
pip install -r requirements.txt
python setup.py develop
```

### 2. Install other dependencies:
```bash
pip install -r requirements.txt
```

## Usage
### 1. Download your trained YOLOv8 weights and place them in:
```bash
drive/MyDrive/Projects/track/best.pt
```

### 2.Place the input video in the same directory:
```bash
drive/MyDrive/Projects/track/15sec_input_720p.mp4
```

### 3.Run the script/notebook

If you're using Google Colab, make sure to mount Google Drive.

## Model Details

### Classes Detected:

0: Ball

1: Goalkeeper

2: Player

3: Referee

### YOLOv8 Detection Model:

Trained to detect the above 4 classes.

Output is passed to the tracker for identity maintenance.

### Re-ID with ResNet18:

Extracts feature embeddings from player crops.

Uses cosine similarity to match players to an existing gallery.

## Output

Output video contains:

Bounding boxes for all detected objects.

Persistent IDs drawn over players using ReID+tracking.

## Notes

ReID is only applied to players for identity consistency.

## Acknowledgements

Ultralytics YOLO

ByteTrack

torchvision models

OneMetric

## License

MIT License (or based on the licenses of used dependencies)









