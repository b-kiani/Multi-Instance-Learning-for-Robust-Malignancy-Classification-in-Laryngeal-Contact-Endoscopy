Patient-Level Gated Multi-Instance Learning for Robust Malignancy Classification in Laryngeal CE-NBI

Official implementation of the experiments described in:
“Patient-Level Gated Multi-Instance Learning for Robust Malignancy Classification in Laryngeal Contact Endoscopy–Narrow Band Imaging”

📌 Overview

This repository contains the full experimental implementation of a patient-level gated multi-instance learning (MIL) framework for automated malignancy classification from Contact Endoscopy combined with Narrow-Band Imaging (CE-NBI) sequences.

Unlike conventional image-level approaches, this work explicitly models intra-patient frame heterogeneity, aligning the computational pipeline with real-world clinical decision-making, where diagnosis is determined at the patient level, not per image.

The proposed framework integrates:

A deep convolutional encoder for frame-level feature extraction

A gated multi-instance learning aggregation module

Patient-level classification with statistical and calibration-aware evaluation

🧠 Motivation

CE-NBI enables high-resolution visualization of microvascular patterns in the larynx, supporting early detection of malignancy. However, CE-NBI examinations consist of multiple frames per patient, and these frames often exhibit:

Variable focus and illumination

Partial lesion coverage

Heterogeneous vascular morphology

Non-diagnostic frames

Standard image-level classifiers ignore this variability and may produce unstable patient-level predictions.

This work addresses the gap by:

Treating each patient as a bag of frames (instances)

Learning adaptive attention weights via gated MIL

Producing calibrated and statistically validated patient-level risk scores

🏗 Model Architecture
1️⃣ Frame-Level Encoder

A deep convolutional neural network extracts feature embeddings from individual CE-NBI frames.

2️⃣ Gated Multi-Instance Learning Aggregator

Frame embeddings are aggregated using a gated attention mechanism, allowing the network to:

Assign higher weights to diagnostically informative frames

Suppress noisy or irrelevant frames

Learn patient-specific importance distributions

3️⃣ Patient-Level Risk Prediction

The aggregated representation is passed to a classification head that outputs a malignancy probability.

📊 Experimental Design

Data split: Patient-level partitioning (no leakage between train/validation/test)

Independent test cohort: n = 73 patients

Evaluation metrics:

ROC-AUC

PR-AUC

Balanced Accuracy

Bootstrap confidence intervals

Reliability (calibration) analysis
