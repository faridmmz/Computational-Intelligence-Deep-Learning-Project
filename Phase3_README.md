# Phase 3: Neural Network Implementation

In this phase, we implement a Convolutional Neural Network (CNN) for the classification of EEG data into seizure and non-seizure classes.

## Table of Contents

- [Dataset Preparation](#dataset-Preparation)
- [Classification](#classification)
- [Presentation of Results](#presentation-of-Results)
- [False Alarm Detection](#false-Alarm-Detection)
- [Comprehensive Solution](#comprehensive-Solution)


## Dataset Preparation

1. **Data Source**: The EEG dataset used in this project can be obtained from PhysioNet.
2. **Data Loading**: The dataset consists of EEG signals from multiple patients. Signals containing seizures were identified using a summary text file. A total of 3000 samples were used for the project, with 2400 samples representing normal data and 600 samples containing seizure activity.
3. **Data Preprocessing**: The signals were filtered using a bandpass filter with a range of 0.5 to 40 Hz to remove noise.

## Classification
- **Feature Extraction**: A set of features was extracted from the EEG signals. These features include margin factor, B factor, kurtosis, mean, median, absolute max, variance, crest factor, standard deviation, and root mean square (RMS).
- **Feature Normalization**: All extracted features were normalized to ensure that they have values within the same range.
- **CNN Model**: A CNN model was designed to classify the EEG signals. The CNN model consists of three convolutional layers, one max-pooling layer, and one fully connected layer. Additionally, the extracted features were passed through a size-1 pooling layer. The model uses softmax activation for classification.


## Presentation of Results

- **Model Training**: The model was trained using 80% of the data, while the remaining 20% was used for testing. Training was performed for 20 epochs with a batch size of 2400.
- **Evaluation**: The accuracy and validation accuracy of the model were plotted over epochs to check for overfitting. The model's accuracy on the test data was also calculated.
- **Performance Metrics**: The model's performance on the test data was evaluated using metrics like accuracy, confusion matrix, recall, and precision. Additionally, a receiver operating characteristic (ROC) curve was plotted to assess the model's false alarm rate.
- **Improved Accuracy**: To improve the accuracy, post-processing was applied by examining predictions in groups of 5 samples. If the majority of the samples in a group were classified as seizures, the labels for all samples in that group were set to 1. This was found to improve overall accuracy.


## False Alarm Detection

1. A specific evaluation was conducted to identify false alarms by analyzing test data consisting only of normal EEG signals.
2. The system counted the number of false alarms and identified the duration of each false alarm.
3. A histogram was created to visualize the distribution of false alarm durations.

## Comprehensive Solution
To build a seizure detection system based on the knowledge gained in this project, consider the following steps:

1. **Data Collection**: Collect EEG data from multiple patients. Aim to obtain diverse data representing different seizure patterns.

2. **Data Preprocessing**: Ensure that the collected data is properly filtered and preprocessed to remove noise and artifacts. Bandpass filtering is recommended.

3. **Feature Extraction**: Extract a set of relevant features from the EEG signals. Features should include margin factor, B factor, kurtosis, mean, median, absolute max, variance, crest factor, standard deviation, and root mean square (RMS). Normalize these features to ensure consistency.

4. **Machine Learning Model**: Implement a CNN model for seizure classification. The model should be trained on a diverse dataset containing both seizure and normal data.

5. **Model Evaluation**: Evaluate the model using metrics such as accuracy, confusion matrix, recall, precision, and ROC curves. Apply post-processing techniques to improve accuracy.

6. **False Alarm Detection**: Develop mechanisms to detect false alarms. Analyze the model's performance on normal data and identify false alarm occurrences.

7. **Optimal Sampling Strategy**: Implement a sampling strategy for continuous monitoring. The system should send the last 20 seconds of EEG data to the model every 20 seconds, allowing for real-time detection.

By following these steps and continuously fine-tuning the model with new patient data, the seizure detection system can be made accurate and reliable. Additionally, consider the necessary hardware and software infrastructure to deploy the system within the patient's body and trigger appropriate responses, such as drug administration, when a seizure is detected.

