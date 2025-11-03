# 🩺 Smart Mirror AI Dermatologist (Hailo-8L Edge AI)

**Author:** Nikita K. (@kitakart)  
**Status:** ≈ 90–95 % complete (fully functional GUI + Hailo HEF markers)  
**Hardware:** Raspberry Pi 5 (8 GB) + Hailo-8L AI Accelerator  

---

**First working real-time AI Dermatologist** GUI built on a **Hailo-8L Edge AI accelerator** (2025).  
Entirely developed from scratch — architecture, Dual HEF engine, GUI overlay, and on-device deployment by **Nikita K. (@kitakart).**

---

## 🌍 Overview

This is the **first known real-time AI Dermatology system successfully deployed on a Hailo-8L Edge AI accelerator** — a **pioneering on-device implementation built entirely from scratch on Raspberry Pi 5.**

**Smart Mirror AI Dermatologist** performs live skin-condition analysis directly on edge hardware, using a Tkinter GUI with overlayed AI markers and fully local inference (no cloud processing).  
It’s part of a larger *Smart Mirror AI* concept combining health insights, outfit recognition, and voice assistance.

---

## 🧩 Key Features

- 🧠 **Dual-HEF Inference Engine** – Custom `DualHefEngine` runs multiple Hailo HEF models in parallel.  
- 🖥️ **Live Tkinter GUI** – Real-time camera feed with color-coded AI bounding boxes and markers.  
- ⚙️ **Fully Offline Inference** – All processing performed locally on Hailo-8L.  
- 🪞 **Smart Mirror Integration** – Ready for full-screen display behind a two-way mirror.  
- 🧬 **Dermatology Models** – Classifies acne, eczema, melasma, psoriasis and more in real time.  
- 🧰 **Modular Config** – `/config`, `/models`, and `/ai_features` make the system portable.

---

## ⚙️ Tech Stack

| Category | Tools / Frameworks |
|-----------|--------------------|
| Edge Hardware | Hailo-8L (M.2 HAT on Raspberry Pi 5) |
| Runtime | HailoRT v4.20 |
| GUI | Tkinter + PIL (ImageTk) |
| Language | Python 3.11 |
| Models | HEF (ResNet v1_18, YOLOv8n, Custom Skin Classifier) |
| OS | Raspberry Pi OS Bookworm (64-bit) |

---

## 🧠 Skills Demonstrated

- **Edge AI Deployment** – Integrated HailoRT SDK and optimized inference pipeline for Hailo-8L.  
- **Embedded Systems** – Built complete offline solution on Raspberry Pi 5 + external accelerator.  
- **GUI Development** – Real-time Tkinter app with OpenCV feed and overlay drawing.  
- **Computer Vision** – Skin-region segmentation and condition classification on live video.  
- **System Design** – Modular config architecture and clean launch workflow.  
- **Hardware-Software Integration** – Camera I/O, multi-threading, and dual HEF runtime.

---

## 🧩 How It Works

1. The **camera feed** is captured in real time using OpenCV.  
2. Each frame is sent into the **DualHefEngine**, which executes two Hailo HEF models in parallel:  
   - **Detection model (`yolov8n.hef`)** – Locates skin regions of interest.  
   - **Classification model (`skin_lesion_classifier.hef`)** – Analyzes those regions to predict conditions.  
3. Results are combined and passed to the GUI.  
4. **Tkinter** renders bounding boxes and confidence overlays on the live video feed.  
5. Everything runs **locally on-device** at ~15 FPS on Raspberry Pi 5 + Hailo-8L.

---

## 💡 Conditions Detected / AI Capabilities

| Condition | Description |
|------------|-------------|
| **Acne / Pimples** | Detects active breakouts, highlighted in red overlay regions. |
| **Eczema** | Identifies dry or inflamed skin patches (amber markers). |
| **Melasma** | Detects uneven pigmentation and hypermelanosis (brown overlays). |
| **Psoriasis** | Highlights scaly lesions using blue boundary boxes. |
| **Rosacea** | Detects redness patterns (pink overlays). |
| **Wrinkles / Dryness** | Evaluates texture irregularities and fine lines (purple highlights). |

> Each detection appears as a translucent, color-coded overlay with a label and confidence score beside it.

---

## 🪞 Smart Mirror Integration

- Uses a **monitor placed behind a two-way mirror glass**, powered by the Raspberry Pi 5.  
- The Tkinter GUI runs in fullscreen, turning the mirror into a live AI display.  
- When a user stands in front, the camera feed and AI overlays appear directly on their reflection.  
- Planned extensions include **voice-controlled “Jarvis mode”** and **outfit recognition modules**, combining multiple AI assistants into one interactive mirror.

---

## 🚀 Future Work

- Refine AI marker accuracy and model calibration  
- Add voice assistant (Jarvis mode)  
- Integrate outfit recognition + stylist module  
- Extend to Hailo-10H / 10B hardware  

---

## 🧭 Project Vision

This project is the foundation for **next-generation home health devices**.  
The long-term vision is a **fully interactive Smart Mirror** that merges:
- Dermatology and skincare analysis  
- Outfit recognition and fashion recommendations  
- Voice-driven virtual assistant  
- Edge-AI privacy (no cloud processing)  

---

## 🗂️ Directory Structure

hailo8-ai-dermatologist/
├── smart_mirror_standalone_hailo.py
├── ai_features/
│ └── dermatologist/hailo_dual_hef.py
├── models/
│ ├── skin_lesion_classifier.hef
│ ├── yolov8n.hef
│ └── resnet_v1_18.hef
├── config/
│ ├── derm_hailo.yaml
│ ├── camera.yaml
│ └── smart_mirror_config.yaml
├── requirements.txt
├── start_smart_mirror.sh
└── README.md

---

## ⚡ Installation

```bash
git clone https://github.com/nikitakartsevv/hailo8-ai-dermatologist.git
cd hailo8-ai-dermatologist
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 smart_mirror_standalone_hailo.py

✅ Make sure HailoRT drivers are installed and models exist in /models/.

---
---

Demo:

---

🏆 Credits & Authorship
Developed entirely by Nikita K. (@kitakart) — from architecture design, model integration, GUI, and hardware setup to final on-device deployment.

---

🧩 License
MIT License © 2025 Nikita K.

---

💬 Contact
📧 nkartsev@ucsc.edu
🐙 GitHub @nikitakartsevv
💡 Building the future of on-device AI — one smart mirror at a time.
