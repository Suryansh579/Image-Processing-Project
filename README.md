# 🔍 360° Defect Detection System using YOLOv8 and L27 Optimization

This repository presents a real-time defect detection system designed for small and medium-scale industries. It leverages a **single-camera setup**, optical components, and **YOLOv8** for cost-effective 360° inspection of cylindrical objects. The project also incorporates **L27 orthogonal experimental design** to identify the optimal training configuration.

---

## 🚩 Problem Statement

Small-scale industries often struggle to afford high-end multi-camera quality inspection systems. These systems are expensive and fail to cover the complete 360° surface. To overcome this, we designed a **low-cost solution using a single camera and mirror assembly** for full-surface inspection and a **line-scan camera for label detection**, achieving comprehensive inspection with minimal hardware.

---

## ⚙️ Project Modules

### 📦 Module 1: Mirror Assembly Setup
- Inspects bulb bases, hex nuts, fasteners
- Single area scan camera + 6-mirror conical assembly
- Captures full 360° object surface in one shot

### 🏷️ Module 2: Label Detection Setup
- Line scan camera + rotating bottle mount
- Captures stitched panoramic label image
- Inspects label misalignment, smudging, missing print

---

## 🖼️ Image Processing Pipeline

1. **Image Acquisition**: High-res images captured using line/area scan cameras
2. **Preprocessing**: Edge enhancement, contrast normalization, blur, exposure variations
3. **Annotation**: Manual bounding boxes using LabelImg and Roboflow
4. **Model Training**: YOLOv8 with tuned hyperparameters on Google Colab (GPU)
5. **Testing**: Real-time predictions with bounding boxes & confidence scores

---

## 🧪 L27 Orthogonal Array Experiments

To fine-tune model performance, 27 experiments were conducted using **Taguchi’s L27 orthogonal design**. Parameters tested include:

- Learning Rate
- Batch Size
- Optimizer (SGD, Adam)
- Epochs
- Image Size
- Augmentation settings

**Minitab** was used for **factor analysis**, and graphs were plotted to identify the best combinations, significantly improving accuracy.

📁 All experiment results can be found in `/L27_Experiments/`

---

## 📊 Minitab Graphs – Experimental Results

The following graphs represent the factor analysis of different metrics using Minitab based on L27 experiments:

### 🔹 Precision
![Precision Graph](graphs/precision.png)

### 🔹 Recall
![Recall Graph](graphs/recall.png)

### 🔹 mAP@50-95
![mAP Graph](graphs/map50-95.png)

### 🔹 Computational Time
![Time Graph](graphs/computational_time.png)

> 📌 These graphs were used to identify the best-performing combinations of hyperparameters for training the YOLOv8 model.


---

## 🗂️ Project Structure

