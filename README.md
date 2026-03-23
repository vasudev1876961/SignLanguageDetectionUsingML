#  Sign Language Detection Using Deep Learning

## 📌 Overview

This project presents a **real-time Sign Language Detection system** that translates hand gestures into textual output using **Computer Vision and Deep Learning**. The system leverages **MediaPipe for hand landmark extraction** and an **LSTM-based neural network** to model temporal dependencies in gesture sequences.

The goal is to enable seamless human-computer interaction and assistive communication for individuals with hearing or speech impairments.

---

##  Key Features

*  Real-time hand gesture recognition using webcam
*  Temporal modeling with LSTM for sequence learning
*  Hand landmark extraction using MediaPipe (21 keypoints)
*  Confidence-based prediction filtering
*  Smooth prediction using temporal consistency logic
*  Lightweight and efficient pipeline (edge-compatible)

---

##  System Architecture

```
Input Video (Webcam)
        ↓
Hand Detection (MediaPipe)
        ↓
Keypoint Extraction (21 landmarks → 63 features)
        ↓
Sequence Formation (30 frames)
        ↓
LSTM Model (Deep Learning)
        ↓
Prediction + Threshold Filtering
        ↓
Text Output
```

---

##  Project Structure

```
SignLanguageDetectionUsingML/
│
├── Image/                     # Raw image dataset (A–Z)
├── MP_Data/                  # Processed keypoints (.npy files)
│
├── app.py                    # Real-time inference script
├── collectdata.py            # Dataset creation from images
├── data.py                   # Preprocessing & utility functions
├── function.py               # Model training pipeline
├── trainmodel.py             # LSTM training script
│
├── model.json                # Model architecture
├── model.h5                  # Trained weights
│
└── README.md
```

---

##  Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/SignLanguageDetectionUsingML.git
cd SignLanguageDetectionUsingML
```

### 2. Install Dependencies

```bash
pip install opencv-python numpy mediapipe tensorflow scikit-learn
```

---

## ▶️ Usage

### 🔹 Step 1: Collect Data

Capture gesture images using webcam:

```bash
python collectdata.py
```

---

### 🔹 Step 2: Generate Keypoints

Convert images into landmark-based dataset:

```bash
python data.py
```

---

### 🔹 Step 3: Train Model

Train LSTM model on sequences:

```bash
python trainmodel.py
```

---

### 🔹 Step 4: Run Real-Time Detection

```bash
python app.py
```

---

##  Model Details

* **Input Shape:** (30 frames, 63 features)
* **Architecture:**

  * LSTM (64 units)
  * LSTM (128 units)
  * LSTM (64 units)
  * Dense Layers
* **Output:** Softmax classification (gesture classes)

---

##  Dataset

* Custom dataset collected via webcam
* Each gesture consists of:

  * 30 sequences
  * 30 frames per sequence
* Stored as NumPy arrays (.npy)

---

##  Limitations

* Supports limited gesture classes (currently A–C or A–Z based on configuration)
* Uses only hand landmarks (no facial/body context)
* Fixed ROI may reduce robustness in varying environments
* Does not support continuous sentence formation

---

##  Future Enhancements

* 🧠 Transformer-based sequence modeling
* 👁️ Multi-modal input (face + pose + hands)
* 🗣️ Text-to-speech output integration
* 📱 Mobile deployment using TensorFlow Lite
* 🔍 Explainable AI (Grad-CAM / SHAP)
* 🌐 Web-based interface using Streamlit

---

##  Technologies Used

* Python
* OpenCV
* MediaPipe
* TensorFlow / Keras
* NumPy
* Scikit-learn

---

##  Applications

* Assistive communication tools
* Human-computer interaction systems
* Gesture-based control interfaces
* Educational tools for sign language learning

---



##  Acknowledgements

* Google MediaPipe for real-time hand tracking
* TensorFlow/Keras for deep learning framework
* OpenCV for computer vision support

---
