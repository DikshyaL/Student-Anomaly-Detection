# Student Performance Anomaly Detection System

## Project Overview
This project focuses on detecting abnormal academic behavior patterns in students using unsupervised anomaly detection algorithms.  
The objective is to identify students whose performance, attendance, or study behavior significantly deviates from the majority, which may indicate at-risk, inconsistent, or unusual learning patterns.

Since labeled anomaly data is rarely available in real-world educational systems, this project applies statistical and machine learning–based unsupervised techniques without relying on predefined labels.

---

## Dataset
Source: Kaggle – Student Performance (1 Million Records)  
Size: Approximately 1,000,000 student records  
Type: Synthetic but statistically realistic educational dataset

### Features Used
- weekly_self_study_hours  
- attendance_percentage  
- class_participation  
- total_score  

Categorical fields such as grade and identifiers were excluded from model training to prevent data leakage.

---

## Problem Statement
How can abnormal student academic behavior be detected automatically when no labeled anomaly data is available?

---

## Methodology

### 1. Data Preprocessing
- Selected numerical features only
- Handled missing values
- Applied StandardScaler for feature normalization

---

### 2. Exploratory Data Analysis
- Boxplots used to identify potential outliers
- Correlation heatmap used to analyze relationships between features
- Strong correlation observed between study hours and total score

---

### 3. Anomaly Detection Techniques

#### Z-Score (Statistical Baseline)
- Measures deviation from the mean in terms of standard deviation
- Effective for detecting extreme univariate outliers
- Used as a baseline comparison method

#### Isolation Forest
- Tree-based unsupervised anomaly detection algorithm
- Isolates anomalies using random feature splits
- Anomalies require fewer splits to isolate
- Scales efficiently to large datasets
- Detects complex multivariate anomalies

#### One-Class SVM
- Learns a decision boundary around normal student behavior
- Points outside the boundary are classified as anomalies
- Effective for detecting subtle and contextual anomalies
- Sensitive to feature scaling and hyperparameters

#### Local Outlier Factor (LOF)
- Density-based anomaly detection algorithm
- Compares local density of a point with its neighbors
- Effective in detecting local anomalies within clusters

---

### 4. Dimensionality Reduction and Visualization
- Applied Principal Component Analysis (PCA) to reduce high-dimensional data to two dimensions
- Used PCA scatter plots to visually validate anomaly separation
- Anomalous students appear isolated from dense clusters of normal behavior

---

## Model Comparison

| Method            | Type                  | Key Strength |
|------------------|----------------------|--------------|
| Z-Score          | Statistical           | Detects extreme outliers |
| Isolation Forest | Tree-based ML         | Scalable and balanced detection |
| One-Class SVM    | Boundary-based ML     | Detects subtle anomalies |
| LOF              | Density-based         | Detects local deviations |

Different models identified different subsets of anomalous students, highlighting the importance of using multiple techniques.

---

## Technologies Used
- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- KaggleHub

---

## Key Learnings
- Unsupervised anomaly detection is essential when labeled data is unavailable
- Feature scaling is critical for distance- and boundary-based algorithms
- Different algorithms capture different types of anomalies
- PCA is effective for validating model behavior in high-dimensional data

---

## Future Work
- Implement deep learning–based autoencoder anomaly detection
- Add explainability techniques for feature contribution analysis
- Deploy the system as a web-based analytics dashboard
- Extend the approach to real institutional datasets

---

## Author
Dikshya Lamichhane
Computer Science and Engineering  

