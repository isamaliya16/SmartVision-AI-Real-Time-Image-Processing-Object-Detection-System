<div align="center">
<br>

![Banner](https://capsule-render.vercel.app/api?type=waving&color=0:0B3D6B,50:1A5276,100:2E86C1&height=220&section=header&text=Computer%20Vision%20%7C%20PR-3&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Morphology%20%C2%B7%20Bitwise%20Ops%20%C2%B7%20Face%20Detection%20%C2%B7%20Object%20Detection%20%C2%B7%20Live%20Pipeline)

<br>

[![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge&logo=checkmarx&logoColor=white)](#)
[![Project](https://img.shields.io/badge/Project-PR--3-1A5276?style=for-the-badge&logo=academia&logoColor=white)](#)
[![Face Detector](https://img.shields.io/badge/Face%20Detector-YuNet-16A34A?style=for-the-badge&logo=opencv&logoColor=white)](#)
[![Object Detector](https://img.shields.io/badge/Object%20Detector-YOLOv8n-DC2626?style=for-the-badge&logo=yolo&logoColor=white)](#)

<br>

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV%205.0-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![Ultralytics](https://img.shields.io/badge/Ultralytics-YOLOv8-111F68?style=flat-square)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

</div>

<br>

## 🎬 Video Walkthrough

<div align="center">

[![Watch the Project Walkthrough](https://img.shields.io/badge/▶%20Watch%20Full%20Walkthrough-Google%20Drive-4285F4?style=for-the-badge&logo=google-drive&logoColor=white)](#)

> 🎥 **A complete end-to-end video explanation** of this Computer Vision project — covering pixel-level morphology, bitwise masking and histograms, real face detection with YuNet, real object detection with YOLOv8n, and the combined pipeline with live FPS benchmarking.

> 📌 *Replace the button above with your own recording link before submitting.*

</div>

---

## 🎯 About This Project

> A security camera doesn't need to understand everything in a scene — but it does need to decide, in real time, whether that's a face worth logging or an object worth flagging. Getting there isn't one algorithm; it's a stack of them, each with its own speed and blind spots.

This project builds that stack from the ground up — starting with **pixel-level classical image processing** (no AI at all) and ending with **two real, pretrained deep learning detectors** running together on the same photo. Every stage is tested on real images, not synthetic examples, and every speed claim is a real measured **FPS number**, not a textbook estimate.

<div align="center">

```
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
   8 Real Test Photos → Clean → Mask → Read Histograms
   ───────────────────────────────────────────────────────
   YuNet (Faces)  +  YOLOv8n (80 Object Classes)
   ───────────────────────────────────────────────────────
   Morphology → Bitwise/Histograms → Faces → Objects
                    → Combined Pipeline + FPS
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
```

</div>

<br>

---

## ✨ What Makes This Project Stand Out

<table>
<tr>
<td width="50%" valign="top">

### 🖼️ Real Photos, Real Failure Cases
- 8 real test images — no synthetic dataset, no CSV
- Two people in **sunglasses** (`bus.jpg`) — a real occlusion test
- A person turned **away from the camera** (`basketball1.png`) — a real pose failure
- A hand-built noisy frame to test whether pre-cleaning actually helps
- Every result reported as measured — including where detection failed

</td>
<td width="50%" valign="top">

### 🧠 Two Real AI Models, Not Mocked
- **YuNet** — a lightweight CNN face detector (OpenCV Zoo), with landmarks
- **YOLOv8n** — a full 80-class object detector (Ultralytics)
- Confidence and IoU thresholds tuned and measured, not assumed
- Non-Max Suppression tested directly: 6 clean boxes → 34 duplicates at IoU 0.99

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ⏱️ Everything Timed, Nothing Estimated
- Face-only, object-only, and combined pipeline **FPS measured separately**
- No webcam in the build environment — a simulated live feed fills in automatically, using the exact same detector code a real camera would run
- CPU-only timings throughout, clearly labelled as such

</td>
<td width="50%" valign="top">

### 📊 Classical vs. Deep Learning, Compared Honestly
- Morphology and bitwise ops benchmarked alongside YuNet and YOLO
- A final side-by-side table: what each technique detects, how fast, and when to use it
- Includes a counter-intuitive result: cleaning a noisy frame first **reduced** YOLO's detections

</td>
</tr>
</table>

<br>

---

## 🗺️ Full Project Journey

<div align="center">

| Task | Focus | Key Output |
|:---:|:---|:---|
| 🧹 **Task 1** | Morphological Operations | Erode/dilate/open/close · 3×3 kernel shape × size comparison |
| 🎭 **Task 2** | Bitwise Ops & Histograms | AND/OR/XOR/NOT masking · ROI extraction · brightness/contrast histograms |
| 🟩 **Task 3** | Face Detection (YuNet) | 4 test photos · FPS benchmark · threshold sweep · face-blur anonymisation |
| 🟥 **Task 4** | Object Detection (YOLOv8n) | 3 test photos · FPS benchmark · confidence/IoU tuning · per-class tally |
| 🔗 **Task 5** | Integrated Pipeline | Combined face+object pipeline · pre-cleaning test · FPS comparison · final table |

</div>

<br>

---

## 🔍 The Toolkit

<div align="center">

<table>
<tr><th>Component</th><th>What It Is</th><th>Used For</th></tr>
<tr><td><code>face_detection_yunet_2023mar.onnx</code></td><td>A small CNN face detector (OpenCV Zoo)</td><td>🟩 Task 3 &amp; 5 — face boxes + 5 landmarks</td></tr>
<tr><td><code>yolov8n.pt</code></td><td>YOLOv8 "nano" — the smallest, fastest YOLOv8 variant</td><td>🟥 Task 4 &amp; 5 — 80-class object boxes</td></tr>
<tr><td><code>bus.jpg</code>, <code>zidane.jpg</code>, <code>messi5.jpg</code>, <code>basketball1.png</code></td><td>Real photos with people, faces, and everyday objects</td><td>Face &amp; object detection tests</td></tr>
<tr><td><code>baboon.jpg</code>, <code>fruits.jpg</code>, <code>smarties.png</code></td><td>Textured / solid-colour real photos</td><td>Morphology, bitwise masking, histograms</td></tr>
</table>

> ⚠️ **No physical webcam in this build environment.** The "real-time" cells try `cv2.VideoCapture(0)` first, exactly as they would on a real machine, and automatically fall back to a simulated feed (the same photo, replayed with small per-frame noise) only if no camera is found. On a machine with a real webcam, the exact same code runs live.

</div>

<br>

---

## 🛠️ Detection Pipeline

<div align="center">

```
Real photo (e.g. bus.jpg)
        ↓
Task 1-2: clean noise, mask regions, check histograms  (classical, no AI)
        ↓
        ├──────────────┐
        ↓              ↓
  YuNet (faces)   YOLOv8n (objects)
  green boxes     red boxes + labels
        ↓              ↓
        └──────┬───────┘
               ↓
     Combined output — one photo, both detectors
               ↓
     FPS measured: face-only · object-only · combined
```

</div>

<br>

---

## ⚙️ At a Glance

<div align="center">

<table>
<tr>
<td align="center" width="33%">

### 🟩 Face Detection
**16 FPS, CPU only**
<br>
Found faces through sunglasses
<br>
Missed a face turned fully away

</td>
<td align="center" width="33%">

### 🟥 Object Detection
**13 FPS, CPU only**
<br>
80 COCO classes in one model
<br>
Confidence &amp; IoU both tuned live

</td>
<td align="center" width="33%">

### 🔗 Combined Pipeline
**7.4 FPS, CPU only**
<br>
Both detectors, one frame
<br>
Slower than either alone, as expected

</td>
</tr>
</table>

</div>

<br>

---

## 🏆 The Technique Progression

<div align="center">

<table>
<tr>
<td align="center" width="25%">

### 🧹 Morphology
**Erode · Dilate · Open · Close**
<br><br>
RECT 3×3 (open+close) gave the cleanest noise removal — bigger kernels distorted the shape more.
<br><br>
**No AI needed**

</td>
<td align="center" width="25%">

### 🎭 Bitwise + Histograms
**AND / OR / XOR / NOT**
<br><br>
Used to cut a circular region out of a real photo and read its brightness as a graph.
<br><br>
**Pixel-level only**

</td>
<td align="center" width="25%">

### 🟩 YuNet
**Face detector**
<br><br>
2 faces found in `bus.jpg` despite sunglasses; 0 faces found in `basketball1.png` — both people faced away.
<br><br>
**16 FPS**

</td>
<td align="center" width="25%">

### 🟥 YOLOv8n
**Object detector**
<br><br>
Found 3-9 objects per photo across the test set; IoU=0.99 exposed 34 duplicate boxes on one bus photo.
<br><br>
**13 FPS**

</td>
</tr>
</table>

</div>

<div align="center">

> 💡 **Key insight:** more preprocessing isn't automatically better. Running a noisy frame through morphological opening *reduced* YOLO's detections from 6 objects to 4 — the smoothing removed fine edge detail the model actually relied on. The lesson mirrors Task 3's finding on pose vs. occlusion: **sunglasses didn't fool YuNet, but a face turned away did** — the failure mode you'd guess isn't always the real one, which is exactly why every stage here was tested, not assumed.

</div>

<br>

---

## 📈 Results Summary

<div align="center">

| Technique | Type | Detects | Lighting Robustness | Speed | Best Use Case |
|:---|:---:|:---|:---:|:---:|:---|
| Morphology (erode/dilate/open/close) | Classical | Shapes/noise in binary images | N/A (binary input) | Very Fast | Cleaning masks before detection |
| Bitwise Ops + Histograms | Classical | Masked regions, brightness info | Low (raw pixel based) | Very Fast | ROI extraction, exposure check |
| **YuNet Face Detector** | Deep Learning | Human faces + landmarks | Medium–High | **16 FPS** | Face-only apps (attendance, blur) |
| **YOLOv8n Object Detector** | Deep Learning | 80 object classes | High | **13 FPS** | General scene understanding |

*Per-image detection counts, the IoU/confidence sweeps, and the full pre-cleaning comparison are in the notebook's Task 3-5 sections.*

</div>

<br>

---

## 🤔 Which Technique for Which Purpose?

<div align="center">

<table>
<tr>
<td align="center" width="20%">

### 🧹 Morphology
**Clean before you detect**
<br>
A small 3×3 kernel with open+close removed noise here without distorting the shape — always start small, bigger isn't automatically better.

</td>
<td align="center" width="20%">

### 🎭 Bitwise/Histograms
**Cheap sanity checks**
<br>
Near-zero cost, so run a histogram check before any detector call — it catches a badly-exposed frame for free.

</td>
<td align="center" width="20%">

### 🟩 YuNet
**Face-only products**
<br>
Handles sunglasses fine; won't find a face that isn't at least partly facing the camera — plan camera angles accordingly.

</td>
<td align="center" width="20%">

### 🟥 YOLOv8n
**General scene understanding**
<br>
One model, 80 classes — the right default when you don't know in advance what you're looking for.

</td>
<td align="center" width="20%">

### 🔗 Combined
**Only when you need both**
<br>
Roughly halves your FPS versus either model alone — reserve it for when the application genuinely needs faces *and* objects.

</td>
</tr>
</table>

</div>

<br>

---

## 🧪 What This Project Covers (Theory)

<details>
<summary><b>📖 Click to expand — Computer Vision Concepts Covered</b></summary>
<br>

- Why erosion is a local "minimum filter" and dilation a local "maximum filter"
- Why opening removes small noise specks while closing fills small holes — and why a combination is often needed for true salt-and-pepper noise
- Why kernel **shape** (rect/ellipse/cross) changes edge smoothness, independent of kernel size
- How bitwise AND/OR/XOR/NOT on binary masks enables Region-of-Interest extraction and image compositing
- Why a histogram is the right tool to diagnose an over- or under-exposed frame, and how alpha/beta adjustment shifts it
- Why YuNet predicts 5 facial landmarks alongside every bounding box, not just a box
- The score-threshold trade-off: catching more faces vs. more false alarms
- Why YOLO looks at the whole image once (single-stage detection) instead of scanning region by region
- How Non-Max Suppression uses the IoU threshold to decide which overlapping boxes are "the same object" — and what happens when that threshold is set too high
- Why classical pre-processing (morphology) can sometimes *hurt* a deep learning model instead of helping it

</details>

<br>

---

## 📁 Repository Structure

```
computer-vision-pr3/
│
├── 📓 CV_PR3.ipynb             ← Full notebook — data to final pipeline (zero errors)
├── 🖼️ data/images/              ← 8 real test photos (place alongside the notebook)
├── 🧠 data/models/              ← face_detection_yunet_2023mar.onnx + yolov8n.pt
├── 📊 plots/                    ← All saved chart images (grids, comparisons, results table)
├── 🌐 CV_PR3_overview.html      ← Short, plain-English project explainer (white theme)
├── 📋 requirements.txt          ← Library versions
└── 📖 README.md                 ← This file
```

*Note: YOLOv8n's weights auto-download on first run via `ultralytics`; the YuNet `.onnx` file must be downloaded separately from the [OpenCV Zoo](https://github.com/opencv/opencv_zoo) and placed in `data/models/`.*

<br>

---

## 📦 Requirements

```
opencv-python==5.0.0.*
opencv-contrib-python==5.0.0.*
ultralytics
numpy
matplotlib
pandas
jupyter
```

<br>

---
## 👨‍💻 Author

<div align="center">

<img src="https://avatars.githubusercontent.com/u/00000000?v=4" width="100" height="100" style="border-radius:50%;" alt="Author"/>

### **Ayush Isamaliya**
*Data Science & Aspiring ML Engineer*

</div>

---

### 🌐 Connect With Me

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-isamaliya16-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/isamaliya16)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ayush_Isamaliya-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ayush-isamaliya-686533312/)

</div>

<br>



<div align="center">

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:2E86C1,100:0B3D6B&height=130&section=footer)

**Built as part of the Deep Learning track at Red & White Skill Education**

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=14&duration=4000&pause=1500&color=888888&center=true&vCenter=true&width=560&lines=Thank+you+for+reviewing+this+project!;Star+%E2%AD%90+if+you+found+it+insightful." alt="Footer Typing" />

*Made with ❤️ | Computer Vision PR-3 | Morphology + Bitwise Ops + YuNet + YOLOv8n | Real-Time Detection Pipeline*

</div>
