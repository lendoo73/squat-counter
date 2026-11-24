# YOLOv7 Squat Counter

Counts squats in a video or webcam stream by estimating pose keypoints and tracking the hip-knee-heel angle with YOLOv7.

Course: [YOLO Masterclass: Deep Learning & Computer Vision](https://www.udemy.com/course/yolo-masterclass-deep-learning-computer-vision-course/)

## Setup

Use Python 3.11, then install the pinned dependencies:

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

The official `yolov7-w6-pose.pt` model is not included. Download the pose checkpoint from the [upstream YOLOv7 project](https://github.com/WongKinYiu/yolov7) and place it in this directory.

## Run

Process the included sample video:

```powershell
python squat_counter.py --weights yolov7-w6-pose.pt --source inference/squat1.mp4 --kpt-label --view-img
```

Use `--source 0` for the default webcam. Add `--nosave` to avoid writing an annotated output video. Run `python squat_counter.py --help` for all options.

## Credits and licensing

The vendored `models/` and `utils/` code is derived from [WongKinYiu/yolov7](https://github.com/WongKinYiu/yolov7), which is licensed under [GNU GPL-3.0](https://github.com/WongKinYiu/yolov7?tab=GPL-3.0-1-ov-file). The squat counter adapts the YOLOv7 pose implementation.

The sample video is included with permission and is not covered by the YOLOv7 software license.
