# 🎵 Music Source Separation using Classical & Deep Learning Methods

## 📌 Overview

This project focuses on **music source separation**, i.e., extracting **drums, bass, vocals, and other components** from an input audio mixture using a multi-stage pipeline of:

1. **Frequency Thresholding (Stage 1)**  
2. **Spectrogram Masking via NMF (Stage 2)**  
3. **Classical Machine Learning (Stage 3)**  
4. **Deep Learning Enhanced U-Net Model (Stage 4)**  
5. **Streamlit Web App for real-time inference (Stage 5)**  

Dataset used: **MUSDB18 (for training and evaluation)** and any custom `.wav` file for the Streamlit app.

---

## 🎯 Problem Statement

In music signal processing, isolating instruments or vocals from a full audio mix is crucial for remixing, karaoke, and music analysis. This project implements multiple methods to evaluate and compare their efficiency in real-world scenarios.

---

## 📌 Pipeline Stages

# Stage 1: Frequency Thresholding (stage1_frequency_thresholding.py)

Approach: Band-pass & high-pass filters using scipy.signal.

Output: Basic frequency-based separation into bass, vocals, drums.

Evaluation: SDR via museval.

# Stage 2: Spectrogram Masking with NMF (stage2_spectrogram_masking.py)

Approach: Non-Negative Matrix Factorization (NMF) applied on magnitude spectrogram.

Separation Logic: Components grouped by frequency bins into bass, vocals, drums.

Output: Improved separation compared to Stage 1.

Evaluation: SDR calculation.

# Stage 3: Classical Machine Learning (stage3_classical_ml.py)

Approach: Random Forest Classifier trained on features like MFCC, Spectral Centroid, Zero-Crossing Rate.

Training: On MUSDB18 (10 training tracks).

Inference: Frame-wise classification with masks applied on STFT.

Output: Separated sources per class.

Evaluation: SDR comparison.

# Stage 4: Deep Learning with Enhanced U-Net (U-Net.py)

Approach: Enhanced U-Net with residual blocks and attention gating.

Input: Magnitude spectrogram.

Output: 4 separated stems (Drums, Bass, Other, Vocals).

Loss: Combined MSE + Spectral Convergence.

Training: Using MUSDB18 with 100 epochs, data augmentation, overlap handling.

Evaluation: SDR via mir_eval.

# Stage 5: Streamlit Web App (app.py)

Functionality: Drag and drop .wav or .mp4 file.

Backend: Loads the trained U-Net (best_model.pth).

Output: Downloads of separated drums, bass, vocals, other.

Run locally :streamlit run app.py
---
## 🎯 Highlights

🛠️ Multiple Techniques: Classical filtering → ML → Deep Learning.

🎧 Real-Time Separation using Streamlit App.

🏆 Enhanced U-Net Model: Residual + Attention for high-quality separation.

📊 SDR Evaluation on MUSDB18 Dataset.

🧪 Support for new audio files during inference (via app).

---

## 🔮 Future Work

Training with larger audio datasets (e.g., MUSDB18HQ).

Apply GAN-based separation models (e.g., Demucs, Open-Unmix).

Add mobile/web deployment.

Improve post-processing (e.g., phase reconstruction, Wiener filtering).


