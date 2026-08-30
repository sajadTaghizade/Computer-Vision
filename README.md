# 👁️ Computer Vision

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-image%20%26%20video-5C3EE8?logo=opencv&logoColor=white)](https://opencv.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras%20CNN-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-U--Net-EE4C2C?logo=pytorch&logoColor=white)](https://pytorch.org/)

Welcome to my **Computer Vision** repository! It contains the computer
assignments and final project for the Fundamentals of Computer Vision
course at the **University of Tehran (UT)**, under **Dr. Seifipour**,
progressing from classical pixel/video-level OpenCV operations, through a
full CAPTCHA-breaking pipeline, to CNN image classification and a
supervised deep-learning image restoration model.

---

## 🛠️ Tech Stack & Tools

| Area | Tools |
|---|---|
| **Classical CV** | OpenCV (`cv2`), NumPy, Pillow |
| **Deep learning** | TensorFlow / Keras (CNN classification), PyTorch (U-Net restoration) |
| **Metrics** | Accuracy, PSNR, SSIM, MSE, MAE |
| **Data** | Hugging Face `datasets`, Google Colab / Drive workflows |

---

## 📂 Repository Layout

```
.
├── CA1/           Image & video fundamentals with OpenCV
├── CA2/           CAPTCHA pipeline: generation, preprocessing, segmentation, recognition
├── CA3/           CNN image classification (Intel Image Classification dataset)
└── FinalProject/  Photo restoration with a U-Net (denoising, scratches, color loss)
```

---

## 📦 Assignments Overview

### [CA1 — Image & Video Fundamentals](./CA1)
Core OpenCV operations and color-model theory: inspecting an image's raw
pixel data and channel layout, converting between color spaces (BGR/RGB and
beyond) with a full written comparison of color models, and loading/probing
a video file (`VideoCapture`, frame properties, frame extraction).

### [CA2 — Breaking CAPTCHAs](./CA2)
A complete, four-part CAPTCHA pipeline built end to end:
1. **Generation** — synthetic CAPTCHA images produced with Pillow (random
   text, fonts, and noise).
2. **Preprocessing** — denoising with spatial low-pass (blurring) filters.
3. **Segmentation** — isolating individual characters via connected-component
   analysis and resizing them to a fixed `64x64` size.
4. **Recognition** — matching each segmented character against a labeled
   reference set (`Mapset`) and writing the decoded results to CSV.

### [CA3 — CNN Image Classification](./CA3)
A convolutional neural network (Keras `Sequential`, built-in
flip/rotation/zoom augmentation, `Rescaling` normalization) trained to
classify the **Intel Image Classification** dataset into 6 scene categories
(buildings, forest, glacier, mountain, sea, street), evaluated on a held-out
test split after training.

### [Final Project — Deep Photo Restoration](./FinalProject)
A supervised **U-Net** (PyTorch) trained to restore damaged photographs —
noise, scratches, and color loss — back toward their clean originals, using
paired damaged/clean image data from Hugging Face Hub. Trained with L1 loss
and Adam for sharper, less over-smoothed restorations than an MSE objective,
and evaluated with the standard restoration-quality metrics:

| | MSE | MAE | PSNR (dB) | SSIM |
|---|---:|---:|---:|---:|
| **U-Net (test set)** | 0.00795 | 0.0579 | 22.997 | 0.8626 |

See [`CV_Final_Project_Report.pdf`](./FinalProject/CV_Final_Project_Report.pdf)
for the full write-up, [`loss_curve.png`](./FinalProject/loss_curve.png) for
the training curve, and
[`sample_restorations.png`](./FinalProject/sample_restorations.png) for
damaged/ground-truth/restored comparisons.

---

## 🚀 Getting Started

Each `CAn`/`FinalProject` folder is a self-contained Jupyter notebook —
open the `.ipynb` file and run it top to bottom. `CA1`/`CA2` run locally
with OpenCV/Pillow; `CA3` and `FinalProject` are written for Google Colab
(Drive-mounted datasets / Hugging Face Hub downloads) but run anywhere with
TensorFlow or PyTorch installed. Each `Descriptions.pdf`/report PDF in the
same folder is the original assignment description or final write-up.

---

## 📄 License

This repository is shared for educational purposes. See individual
assignment folders for any assignment-specific licensing notes.
