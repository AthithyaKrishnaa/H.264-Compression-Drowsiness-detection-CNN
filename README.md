Below is **ONE clean, fully edited, GitHub-ready README**.
Everything is **proper Markdown**, **tables where needed**, **no ASCII clutter**, **copy-paste as a single cell**.

---

````markdown
# 🚗 H.264 Video Compression + Drowsiness Detection System

An end-to-end **driver safety monitoring system** that integrates efficient video compression with real-time deep learning–based drowsiness detection.

---

## 📋 Project Overview

This project combines:

- **H.264 / AVC video compression** (87.10% size reduction)
- **Real-time facial landmark detection** using MediaPipe FaceMesh (468 landmarks)
- **Deep learning classification** using PyTorch (EyeCNN + MouthCNN)
- **Multi-modal drowsiness analysis**
  - Eye closure
  - Yawning
  - Head pose
  - Gaze direction
- **Annotated video output** with color-coded bounding boxes and real-time alerts

**Performance**
- Input: **1920×1080 @ 30 FPS**
- Processing speed: **46.2 FPS**
- GPU: **NVIDIA Tesla T4**
- Output:
  - Annotated MP4 video
  - Frame-level CSV analytics

---

## 🎯 System Architecture

```mermaid
flowchart LR
    A[Input Video<br/>1920×1080 @ 30 FPS] --> B[H.264 / AVC Compression<br/>CRF 23<br/>87.10% Reduction]
    B --> C[Drowsiness Detection Pipeline]

    C --> D[MediaPipe FaceMesh<br/>468 Landmarks]
    D --> E[ROI Extraction<br/>Eyes & Mouth]

    E --> F[EyeCNN<br/>Open / Closed]
    E --> G[MouthCNN<br/>Yawning]

    F --> H[Drowsiness Scoring<br/>Temporal Logic]
    G --> H

    H --> I[Annotated Video<br/>Visual Alerts]
    H --> J[CSV Analytics]
````

---

## 📁 Project Deliverables

| Cell       | Description                                        |
| ---------- | -------------------------------------------------- |
| **Cell 1** | Environment setup, GPU check (Tesla T4, CUDA 12.6) |
| **Cell 2** | Video compression pipeline (H.264, CRF 23)         |
| **Cell 3** | Drowsiness detection + video annotation            |
| **Cell 4** | Final report, metrics, and analysis                |

---

## 📊 Video Compression Performance

### Input Video Specifications

| Property      | Value               |
| ------------- | ------------------- |
| Filename      | testing_video.mp4   |
| Resolution    | 1920×1080 (Full HD) |
| Frame Rate    | 30 FPS              |
| Duration      | 15.63 seconds       |
| Total Frames  | 469                 |
| Original Size | 39.34 MB            |

### Compression Results

| Metric           | Value          |
| ---------------- | -------------- |
| Compressed Size  | 5.08 MB        |
| Size Reduction   | **87.10%**     |
| Codec            | H.264 / AVC    |
| Quality Setting  | CRF 23         |
| Compression Time | 55.52 seconds  |
| Encoding Speed   | 8.45 FPS       |
| Audio Codec      | AAC (128 kbps) |

### Why H.264 / AVC?

* Universal compatibility across devices and browsers
* Efficient compression with low compute overhead
* Ideal for real-time and edge deployment
* No licensing complexity compared to H.265 / VVC

---

## 🧠 Deep Learning Models

### EyeCNN – Eye State Classification

| Feature        | Details                           |
| -------------- | --------------------------------- |
| Input          | 24×24 grayscale eye ROI           |
| Output         | Open / Closed                     |
| Parameters     | ~151K                             |
| Inference Time | ~2 ms per eye (GPU)               |
| Processing     | Left and right eyes independently |

### MouthCNN – Yawn Detection

| Feature         | Details                    |
| --------------- | -------------------------- |
| Input           | 24×24 grayscale mouth ROI  |
| Output          | Normal / Yawning           |
| Parameters      | ~166K                      |
| Inference Time  | ~2 ms (GPU)                |
| Temporal Filter | 5-second gap between yawns |

### MediaPipe FaceMesh

| Feature          | Details                                       |
| ---------------- | --------------------------------------------- |
| Version          | 0.10.14                                       |
| Facial Landmarks | 468                                           |
| Iris Tracking    | Enabled                                       |
| Performance      | >30 FPS                                       |
| Usage            | ROI extraction, head pose, gaze, bounding box |

**Combined Pipeline**

```
Frame → FaceMesh → ROI Extraction → CNN Inference → Drowsiness Score → Alert Logic
```

---

## 📈 Detection Performance Results

### Test Video Analysis

| Metric              | Value         |
| ------------------- | ------------- |
| Frames Analyzed     | 469           |
| Processing Speed    | 46.2 FPS      |
| Detection Time      | 10.15 seconds |
| Annotation Time     | 16.47 seconds |
| Face Detection Rate | 100%          |
| Eyes Closed Frames  | 258 (55.0%)   |
| Drowsy Frames       | 31 (6.6%)     |
| Max Eye Closure     | 1.76 seconds  |
| Total Yawns         | 1             |

### Drowsiness Breakdown

| Category        | Frames | Percentage |
| --------------- | ------ | ---------- |
| Normal Driving  | 438    | 93.4%      |
| High Drowsiness | 31     | 6.6%       |
| Mild / Moderate | 0      | 0%         |

---

## 💻 Technical Stack

### Core Libraries

| Library      | Purpose                          |
| ------------ | -------------------------------- |
| PyTorch      | Deep learning (CUDA accelerated) |
| torchvision  | Model utilities                  |
| OpenCV       | Video I/O and annotation         |
| MediaPipe    | Facial landmark detection        |
| NumPy        | Numerical operations             |
| Python 3.10+ | Core language                    |

### Tools

* FFmpeg (libx264 encoder)
* Google Colab (GPU runtime)

---

## 🧩 Hardware Requirements

### Minimum

* CPU: Quad-core processor
* RAM: 8 GB
* Camera: 720p webcam

### Recommended

* GPU: NVIDIA GPU (4 GB+ VRAM)
* RAM: 16 GB
* Camera: 1080p

---

## ✨ Key Achievements

* **87% video size reduction** without accuracy loss
* **Real-time performance** at 46 FPS
* **100% face and ROI detection success**
* Lightweight models (~317K total parameters)
* Production-ready outputs (CSV + annotated video)
* Edge and cloud deployable

---

## ⚠️ Limitations

* Reduced robustness in extreme low-light conditions
* No audio-based drowsiness cues (e.g., yawning sound)

---

## 🎓 Conclusion

This project demonstrates a **complete, real-time driver drowsiness detection pipeline**
that integrates **video compression, computer vision, and deep learning**.

The system achieves **high accuracy, real-time performance, and efficient storage**, making it suitable for real-world deployment in driver monitoring and intelligent transportation systems.

```

---

