# ADHD detection using ML 
Classification of ADHD (61) vs Non-ADHD (60) children (ages 7–12) using EEG and machine learning

# Project Overview
This repository contains a Google Colab notebook and dataset for building and evaluating models that classify ADHD vs non-ADHD children using EEG recordings. The project compares classical ML algorithms (Random Forest, SVM, Logistic Regression) with deep learning approaches (CNN, a 5-layer vanilla feedforward network, and a feedforward network with residual connections).

Key points:

Total subjects: 121 (61 ADHD, 60 non-ADHD)

Ages: 7–12 years

EEG channels: 19

Sampling frequency: 256 Hz

Timestamps per recording: variable as per recordings

The notebook provides a reproducible pipeline: preprocessing → feature extraction → model training → evaluation.

# Repo Structure

ADHD-detection-using-ML/

├─ ADHD.zip # EEG dataset (compressed)

├─ ADHD_detection.ipynb # Google Colab notebook with full pipeline

├─ README.md # ← this file

# Data

The dataset is provided as ADHD.zip. Unzip it to access the EEG data files.

# Format

Each subject: multichannel EEG time series (19 channels).

File format: .mat with shape [timestamp, channel].

Labels: 0 = non-ADHD, 1 = ADHD.

# Procedure

1. Load and Extract Data

  - Upload the dataset (ADHD.zip) to your Colab environment.

  - Unzip the files for access.

2. Preprocessing Functions

  - Define EEG frequency bands (delta, theta, alpha, beta, gamma).

  - Implement bandpass and notch filters for noise removal.

  - Define a function to compute Power Spectral Density (PSD).

3. Feature Extraction

  - Load .mat EEG files for both ADHD and Control groups.

  - Apply filtering → extract PSD features for each channel and band.

   -Store results in Pandas DataFrames.

4. Dataset Construction

  - Convert per-subject PSD values into feature vectors (Channel × Band).

  - Flatten into a single row per subject.

  - Merge ADHD and Control datasets into a feature matrix (subjects × features) with labels.

5. Model Training

   - Define features (X) and labels (y).

   - Train multiple classifiers with 5-fold cross-validation:

   - Random Forest

   - Logistic Regression

   - Support Vector Machine (SVM)

   - CNN

   - 5 Layer Vanilla FFN

   - FFN with Residual Connection

6. Evaluation

  - Compare accuracies of all models.

  - Select the best-performing model for ADHD detection.
