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
