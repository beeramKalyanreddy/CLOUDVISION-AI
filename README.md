# ☁️ CloudVision AI

### An AI-Based Temporal Swin Transformer Framework for Cloud Removal and Surface Reconstruction in LISS-IV Imagery

CloudVision AI is an AI-based remote sensing framework designed to reconstruct cloud-covered regions in **LISS-IV satellite imagery**. The system uses a **Temporal Swin Transformer** to learn spatial and temporal patterns from recent and historical observations and generate cloud-free surface information.

The proposed approach uses only **LISS-IV imagery**, without depending on external SAR/optical satellite data or future observations.

---

## 📌 Table of Contents

* [Overview](#-overview)
* [Problem Statement](#-problem-statement)
* [Objectives](#-objectives)
* [Proposed System](#-proposed-system)
* [Key Features](#-key-features)
* [System Workflow](#-system-workflow)
* [Technologies Used](#-technologies-used)
* [Hardware Requirements](#-hardware-requirements)
* [Software Requirements](#-software-requirements)
* [Project Structure](#-project-structure)
* [Applications](#-applications)
* [Advantages](#-advantages)
* [Limitations](#-limitations)
* [Future Scope](#-future-scope)
* [Conclusion](#-conclusion)
* [Team](#-team)

---

## 🔍 Overview

Persistent cloud cover is a major challenge in optical remote sensing because clouds can hide important surface information in satellite images.

LISS-IV provides high-resolution imagery useful for:

* Land-use mapping
* Agriculture
* Disaster management
* Environmental monitoring

Traditional cloud masking methods remove cloud-covered pixels but do not recover the information hidden underneath.

CloudVision AI addresses this problem using a **Temporal Swin Transformer**, which learns from the current cloudy image together with recent and historical LISS-IV observations.

---

## ❗ Problem Statement

The project focuses on the following problems:

1. Persistent cloud cover causes significant information loss in LISS-IV imagery.
2. Traditional cloud masking discards cloud-covered pixels.
3. Existing approaches may depend on external SAR or optical satellite data.
4. Preserving fine spatial details during reconstruction is challenging.
5. Maintaining spectral consistency in reconstructed regions is important.
6. A temporal reconstruction framework is required using historical LISS-IV observations.

---

## 🎯 Objectives

The main objectives of CloudVision AI are:

* Detect cloud-covered regions in LISS-IV imagery.
* Utilize recent observations from approximately **5–10 days**.
* Utilize historical observations of up to **one month**.
* Learn spatial and temporal surface patterns.
* Reconstruct cloud-occluded regions.
* Preserve fine spatial details.
* Maintain spectral consistency.
* Reduce dependency on external satellite sensors.
* Generate reliable cloud-free imagery for practical applications.

---

## 🚀 Proposed System

The proposed system consists of three major stages:

### 1. Cloud Detection

The system identifies cloud-covered regions in the current LISS-IV image.

### 2. Temporal Swin Transformer

A Temporal Swin Transformer learns spatial and temporal patterns using:

* Current cloudy LISS-IV imagery
* Recent observations from 5–10 days
* Historical observations up to one month

### 3. Surface Reconstruction

The learned information is used to reconstruct cloud-occluded regions while attempting to preserve:

* Spatial details
* Surface structure
* Spectral consistency

The overall proposed approach is based entirely on the temporal history of LISS-IV imagery.

---

## ⭐ Key Features

* ☁️ Cloud detection
* 🛰️ LISS-IV satellite image processing
* 🧠 Temporal Swin Transformer
* 🕒 Multi-temporal image analysis
* 🖼️ Cloud-region reconstruction
* 🔬 Spatial-detail preservation
* 🎨 Spectral consistency
* 🚫 No external SAR data required
* 🚫 No future observations required
* 🌍 Remote sensing applications

---

## 🔄 System Workflow

```text
             LISS-IV Satellite Images
                       │
                       ▼
              Image Preprocessing
                       │
                       ▼
                Cloud Detection
                       │
                       ▼
        ┌─────────────────────────────┐
        │     Temporal Image Data     │
        │                             │
        │ Current Image               │
        │ Recent 5–10 Day Images      │
        │ Historical Images           │
        │ Up to 1 Month               │
        └─────────────────────────────┘
                       │
                       ▼
          Temporal Swin Transformer
                       │
                       ▼
            Surface Reconstruction
                       │
                       ▼
             Cloud-Free LISS-IV
                  Imagery
```

---

## 🧠 Why Temporal Swin Transformer?

Traditional CNN-based approaches primarily focus on local spatial patterns.

A Transformer-based architecture can model broader relationships within image regions. CloudVision AI extends this concept temporally by using observations from different time periods.

This allows the model to learn how surface patterns change over time and use those observations when reconstructing cloud-covered areas.

---

## 🆚 Existing System vs Proposed System

| Existing Approach        | Limitation                                            |
| ------------------------ | ----------------------------------------------------- |
| Cloud Masking            | Discards cloud-covered information                    |
| SAR-Optical Fusion       | Requires external SAR data                            |
| CNN-based Reconstruction | Limited long-range temporal modeling                  |
| Diffusion Models         | High computational cost                               |
| Multi-sensor Methods     | Requires multiple data sources                        |
| **CloudVision AI**       | Uses temporal LISS-IV observations for reconstruction |

The literature survey in the project compares approaches including SAR–Optical Fusion CNN, PMAA, Cloudformer, CloudTran++, CRformer, SeqDM, and SwinIR.

---

## 🛠️ Technologies Used

### Programming Language

```text
Python
```

### Deep Learning

```text
PyTorch
Temporal Swin Transformer
TensorFlow (Optional)
```

### Image Processing

```text
NumPy
OpenCV
```

### Geospatial Processing

```text
GDAL
Rasterio
```

### Visualization

```text
Matplotlib
QGIS
```

### Development Environment

```text
VS Code
PyCharm
Jupyter Notebook
```

The presentation specifies Python, PyTorch, NumPy/OpenCV, GDAL/Rasterio, VS Code/PyCharm, Jupyter, Matplotlib, and QGIS as the main software environment.

---

## 💻 Software Requirements

| Component        | Requirement             |
| ---------------- | ----------------------- |
| Operating System | Windows / Linux         |
| Recommended OS   | Ubuntu for GPU training |
| Language         | Python                  |
| Deep Learning    | PyTorch                 |
| Image Processing | NumPy, OpenCV           |
| Geospatial       | GDAL, Rasterio          |
| IDE              | VS Code / PyCharm       |
| Notebook         | Jupyter Notebook        |
| Visualization    | Matplotlib / QGIS       |

---

## 🖥️ Hardware Requirements

| Component       | Requirement                             |
| --------------- | --------------------------------------- |
| CPU             | Intel i7/i9 or AMD Ryzen 7/9 equivalent |
| GPU             | NVIDIA RTX 3060 or higher               |
| CUDA            | Required for GPU training               |
| RAM             | Minimum 16 GB                           |
| Recommended RAM | 32 GB                                   |
| Storage         | 500 GB+ free SSD                        |
| Cloud           | Google Colab / AWS optional             |
| Backup          | External drive / NAS                    |
| Power           | UPS recommended                         |

These requirements are taken from the project's hardware specification.

---

## 📁 Project Structure

A recommended implementation structure is:

```text
CloudVision-AI/
│
├── dataset/
│   ├── raw/
│   ├── preprocessed/
│   └── temporal/
│
├── models/
│   ├── cloud_detector.py
│   ├── temporal_swin.py
│   └── reconstruction.py
│
├── preprocessing/
│   ├── preprocessing.py
│   ├── cloud_mask.py
│   └── geospatial_utils.py
│
├── training/
│   ├── train.py
│   ├── validation.py
│   └── config.py
│
├── inference/
│   └── predict.py
│
├── evaluation/
│   └── metrics.py
│
├── visualization/
│   └── visualize.py
│
├── notebooks/
│
├── requirements.txt
├── README.md
└── LICENSE
```

> **Note:** This is a recommended implementation structure. The presentation specifies the technologies and system modules but does not define an exact source-code folder structure.

---

## 🌍 Applications

CloudVision AI can support applications where cloud-free optical imagery is valuable, including:

### 🌾 Agriculture

Reconstructed imagery can support analysis of agricultural areas when clouds obscure the surface.

### 🚨 Disaster Management

Cloud-free imagery can improve access to surface information during disaster-response scenarios.

### 🗺️ Land-Use Mapping

Reconstructed imagery can help reduce missing regions caused by cloud cover.

### 🌱 Environmental Monitoring

Temporal observations can support monitoring of surface and environmental changes.

These application areas are identified in the project's abstract and conclusion.

---

## ✅ Advantages

* Uses LISS-IV temporal observations.
* Reduces dependence on external satellite sensors.
* Uses both spatial and temporal information.
* Attempts to preserve fine spatial details.
* Considers spectral consistency.
* Can generate cloud-free imagery for downstream applications.
* Designed with real-time applications in mind.

---

## ⚠️ Limitations

The project presentation identifies limitations in existing methods, but it does not provide a finalized experimental limitations section for the proposed implementation.

Potential implementation challenges include:

* Requirement for sufficient historical LISS-IV observations.
* High GPU requirements during Transformer training.
* Large storage requirements for satellite datasets.
* Difficulty reconstructing regions with major surface changes between observations.
* Need for appropriate cloud masks and training data.

---

## 📊 Evaluation

The reconstructed images can be evaluated using image-reconstruction and remote-sensing metrics such as:

```text
PSNR
SSIM
MAE
RMSE
Spectral consistency
```

> These metrics are suggested for implementation/evaluation; the supplied project presentation does not report experimental metric values.

---

## 🔮 Future Scope

Possible future development areas include:

* Improving temporal attention mechanisms.
* Optimizing the model for faster inference.
* Supporting larger LISS-IV datasets.
* Developing an automated cloud-detection pipeline.
* Improving reconstruction quality for thick cloud regions.
* Integrating the system into a practical remote-sensing workflow.
* Deploying the trained model through a web or cloud application.

---

## 🏁 Conclusion

CloudVision AI proposes a Temporal Swin Transformer framework for cloud removal and surface reconstruction in LISS-IV satellite imagery.

Instead of simply discarding cloud-covered pixels or depending on external satellite sensors, the framework uses the surface's own recent and historical observations to learn spatial-temporal patterns.

The proposed approach aims to generate reliable cloud-free imagery while preserving spatial details and spectral consistency. Such reconstructed imagery can support applications including disaster response, agriculture, land-use mapping, and environmental monitoring.

---

## 👥 Team

| Name                | Roll Number |
| ------------------- | ----------- |
| **B. Kalyan Reddy** | 23AG1A0508  |
| **Disha Pandey**    | 23AG1A0514  |
| **K. Sushmitha**    | 24AG5A0505  |

### Project Guide

**Mr. Satish Penumalli**
Assistant Professor
Project Guide

---

## 📜 License

This project is developed for academic and research purposes.

---

## ⭐ Acknowledgement

We thank our project guide and institution for their guidance and support in developing **CloudVision AI – An AI-Based Temporal Swin Transformer Framework for Cloud Removal and Surface Reconstruction in LISS-IV Imagery**.

