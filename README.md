# 🧠 Patient-Level Gated Multi-Instance Learning  
## Robust Malignancy Classification in Laryngeal CE-NBI

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/Framework-PyTorch-red)
![Medical AI](https://img.shields.io/badge/Domain-Medical%20AI-green)
![Status](https://img.shields.io/badge/Status-Research-orange)

---

<p align="center">
  <img src="assets/architecture.png" width="700">
</p>

---

## 📌 Overview

This repository contains the official implementation of a **patient-level gated multi-instance learning (MIL) framework** for automated malignancy classification using **Contact Endoscopy combined with Narrow-Band Imaging (CE-NBI)** sequences.

Unlike conventional image-level approaches, this framework explicitly models **intra-patient frame heterogeneity**, producing **patient-level risk predictions** aligned with real-world clinical decision-making.

---

## 🎯 Motivation

CE-NBI sequences consist of multiple frames per patient. Challenges include:

- Variable lesion visibility  
- Motion artifacts  
- Partial lesion coverage  
- Non-diagnostic frames  

Standard image-level classifiers ignore this variability and can produce unstable patient-level predictions.  

This work treats each patient as a **bag of frames (instances)** and uses **gated attention MIL** to learn which frames are informative.

---

## 🏗 Architecture Overview

```text
CE-NBI Frames (per patient)
            │
            ▼
   Deep CNN Encoder
            │
            ▼
 Gated Attention MIL Module
            │
            ▼
 Patient-Level Risk Prediction
