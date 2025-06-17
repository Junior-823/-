# YZU Garbage Overflow Detector

This project detects garbage bin overflow on YZU campus using OpenCV and Haar Cascade.

## Features
- Custom dataset collection
- Haar Cascade training
- Real-time detection via webcam

## Dataset
Collected around campus (300+ images, annotated with LabelImg)

## Installation
- Install OpenCV: `pip install opencv-python`
- Install LabelImg: `pip install labelImg`

## Usage
- Run real-time detection:
```bash
python garbage_detector.py
