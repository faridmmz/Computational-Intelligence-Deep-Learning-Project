# Phase 2: Feature Engineering and Selection

In this phase, we concentrate on feature engineering, where we extract relevant features from EEG data and evaluate them.

## Table of Contents

- [Feature Selection](#feature-Selection)
- [Evaluating Individual Feature Performance](#evaluating-Individual-Feature-Performance)
- [Analyzing Feature Correlations](#analyzing-Feature-Correlations)
- [Selecting the Best Features](#selecting-the-Best-Features)
- [Improving Accuracy with Segmentation](#improving-Accuracy-with-Segmentation)
- [Conclusion](#Conclusion)


## Feature Selection

In this phase of the project, we focused on feature selection. Feature selection is crucial for building a more efficient and accurate machine learning model. We aimed to identify the most informative features while discarding irrelevant or redundant ones. Our approach involved two main steps: evaluating the individual performance of features and analyzing feature correlations.


## Evaluating Individual Feature Performance

We began by evaluating the performance of each feature on its own. To do this, we used a Decision Tree classifier to classify the data using each feature independently. The accuracy of the classification served as a measure of the quality of the feature in distinguishing between the two classes: normal and seizure.

We tested each of the following features separately:

- A-factor
- B-factor
- Mean
- Absolute Max
- Median
- Variance
- Skewness
- Kurtosis
- Root Mean Square (RMS)
- Crest Factor
- Margin Factor
- Standard Deviation
- Point-to-Point (PTP)

The accuracy of each feature's classification was recorded. This allowed us to identify how well each feature acts on its own to discriminate between the two classes.


## Analyzing Feature Correlations

In the second part of the feature selection process, we analyzed the correlation between features. A good feature is one that has low correlation with other features because highly correlated features often contain similar information, making one of them redundant. To determine these correlations, we used a correlation matrix, which displayed the pairwise correlations between the features.



## Selecting the Best Features

Our goal was to select a set of features that could maximize classification accuracy while minimizing redundancy. To achieve this, we used F1-score as a metric to combine the information obtained from the two steps above. For each feature, we calculated its F1-score by considering its classification accuracy and its correlations with other features. We selected the top five features based on this criterion.

The final set of selected features, along with their F1-scores, is as follows:

- A-factor
- B-factor
- Mean
- Absolute Max
- Margin Factor

These features were found to be the most informative while maintaining low correlation with one another, making them the best choice for building our classification model.

## Improving Accuracy with Segmentation
In the final part of this phase, we aimed to improve the accuracy and efficiency of the classification model by using a segmentation approach. Instead of training the classifier on the entire dataset, we divided the data into clusters using a K-Means clustering algorithm. Each cluster represents a segment of data that shares common characteristics.

We divided the dataset into three clusters and trained separate K-Nearest Neighbors (KNN) classifiers on each cluster. During testing, the algorithm predicts which cluster a given input data point belongs to and uses the corresponding cluster-specific KNN classifier for classification.

The segmentation approach allowed us to capture more fine-grained patterns within the data. It improved accuracy, as evidenced by the increased performance of the KNN classifier. The accuracy of the model improved from 90% to 93% using this approach.

We also explored the idea of using multiple classes, but it resulted in a trade-off between accuracy and the ability to distinguish between different classes. Ultimately, the segmentation approach was more effective in improving accuracy while maintaining the simplicity of a binary classification problem.


## Conclusion
By implementing feature selection and the segmentation technique, we have taken significant steps towards building an intelligent system for detecting seizures in epileptic patients from EEG signals. These methodologies enhance the efficiency and performance of our classification model, and the selected features provide valuable insights into the most relevant aspects of the data. In the next phase of the project, we will continue to refine our system and explore the use of deep learning methods for further improvements.

