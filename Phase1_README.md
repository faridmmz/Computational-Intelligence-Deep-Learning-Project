# Phase 1: Data Acquisition and Preprocessing

Welcome to Phase 1 of our Computational Intelligence Project! In this phase, we aim to implement an intelligent system for detecting seizures in epileptic patients using EEG signals. This README will guide you through the key features, methods, and results of Phase 1.

## Table of Contents

- [Dataset Description](#dataset-Description)
- [Data Preprocessing and Loading](#data-Preprocessing-and-Loading)
- [Feature Engineering](#feature-Engineering)
- [Classification of Signals](#classification-of-Signals)
- [Conclusion](#Conclusion)


## Dataset Description

The dataset provided for this project consists of EEG signals collected from epileptic patients which we got from [CHB-MIT Scalp EEG Database](https://physionet.org/content/chbmit/1.0.0/). It includes 500 signal segments, each 23.6 seconds in length, with a sampling frequency of 173.61 Hz. These signals are categorized into five different groups.


## Data Preprocessing and Loading

The data preprocessing involves several steps, including:

- Loading EEG data
- Removing noise and artifacts
- Segmenting data into epochs
- Extracting useful features
- Labeling data (seizure or non-seizure)


## Feature Engineering

In this phase, we extracted features from the EEG signals. The feature categories include:

- **Statistics**: Features like mean, median, variance, standard deviation, and more.
- **Innovative**: Features such as RMS, crest factor, margin factor, A factor, and B factor.
- **Entropies**: Various entropy-based features.
- **LBP-based features**: Local Binary Pattern (LBP) features.
- **Time Domain**: Features derived from the time domain analysis.
- **Frequency Domain**: Features derived from the frequency domain analysis.

Our goal was to implement at least 15 features from a combination of these categories to represent the EEG signals effectively.


## Classification of Signals

After extracting features, we performed classification using three different algorithms:

- **Support Vector Machine (SVM)** with linear, sigmoid, rbf, and poly kernels.
- **Random Forest (RF)** with varying maximum depths and random states.
- **K-Nearest Neighbors (KNN)** with different numbers of neighbors and weight settings.

To evaluate the performance of each algorithm, we employed k-fold cross-validation (k=5) and then calculated Accuracy, Precision and Recall for each one.

## Conclusion
In Phase 1, we explored the feature engineering and classification of EEG signals for seizure detection. We found that random forest yielded the best results. It's important to note that data normalization may improve efficiency but does not always guarantee increased accuracy.