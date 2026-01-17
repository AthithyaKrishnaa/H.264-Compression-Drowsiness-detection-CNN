# 🚗 H.264 Video Compression + Drowsiness Detection System

An end-to-end **driver safety monitoring system** that integrates efficient video compression with real-time deep learning–based drowsiness detection.

---

## 📋 Project Overview

This project combines:

- **H.264/AVC video compression** (87.10% size reduction)
- **Real-time facial landmark detection** using MediaPipe FaceMesh (468 landmarks)
- **Deep learning classifiers** (EyeCNN + MouthCNN with PyTorch)
- **Multi-modal drowsiness analysis**:
  - Eye closure
  - Yawning
  - Head pose
  - Gaze direction
- **Annotated video output** with real-time alerts

**Performance**
- Input: **1920×1080 @ 30 FPS**
- Processing speed: **46.2 FPS** on **NVIDIA Tesla T4**
- Outputs:
  - Annotated MP4 video
  - CSV analytics (frame-level data)

---

## 🎯 System Architecture
┌──────────────────┐ ┌───────────────────┐ ┌────────────────────┐
│ INPUT VIDEO │──▶│ VIDEO COMPRESS │──▶│ DROWSINESS │
│ testing_video │ │ H.264 / AVC │ │ DETECTION │
│ 39.34 MB │ │ CRF 23 │ │ (GPU Accelerated) │
│ 469 frames │ │ ↓ 87.10% │ │ │
│ 1920×1080@30fps│ │ 5.08 MB │ │ • MediaPipe │
└──────────────────┘ └───────────────────┘ │ FaceMesh │
│ • EyeCNN │
│ • MouthCNN │
│ • Head Pose │
│ • Gaze Tracking │
└────────────────────┘
│
┌───────────────┼──────────────┐
│ │ │
┌──────▼──────┐ ┌─────▼───────┐ ┌────▼────────┐
│ CSV LOG │ │ ANNOTATED │ │ DOWNLOAD │
│ 469 rows │ │ VIDEO MP4 │ │ & STATS │
│ 10 columns │ │ + Alerts │ │ Summary │
└─────────────┘ └─────────────┘ └─────────────┘

