# Neurodegenerative-Disease-Classification-using-Gait-Analysis

## Overview
This project aims to classify neurodegenerative diseases (Parkinson’s, Huntington’s, and ALS) and distinguish them from healthy controls using gait time-series data. The dataset was obtained from the **PhysioNet Gait in Neurodegenerative Diseases Database**. Machine learning models were applied to identify patterns in stride intervals, swing/stance phases, and double support intervals.  

The analysis was conducted using Python libraries such as **pandas, numpy, matplotlib, and scikit-learn**.

## Data Preprocessing

1. **Data Import & Merging:**
   - Loaded `.ts` files containing stride-to-stride gait features for each subject.
   - Merged them into a single dataset with subject ID and disease label.

2. **Metadata Integration:**
   - Added demographic and clinical information (age, gender, height, weight, clinical scores).

3. **Outlier Handling:**
   - Identified and removed sensor-based errors using visual inspection and distribution analysis.

4. **Feature Correlation Check:**
   - Generated a heatmap to detect dependencies; retained only non-redundant features.

5. **Data Normalization:**
   - Normalized stride intervals by subject height to account for variability in body proportions.

6. **Data Augmentation:**
   - Split long time-series recordings into multiple segments to increase sample size and reduce underfitting.

## Exploratory Data Analysis (EDA)

- Visualized class distributions and highlighted class imbalance (e.g., more Huntington’s vs. fewer ALS samples).  
- Plotted gait feature distributions to identify differences between disease groups and controls.  
- Detected outliers in stride intervals caused by faulty sensor readings.  

## Machine Learning Models

### 1. Support Vector Machine (SVM)
- Train Accuracy: **0.82**
- Cross-Validation Accuracy: **0.82 ± 0.02**

### 2. Logistic Regression
- Train Accuracy: **0.76**
- Cross-Validation Accuracy: **0.76 ± 0.01**

### 3. Random Forest
- Train Accuracy: **0.94**
- Cross-Validation Accuracy: **0.92 ± 0.01**
- Test Accuracy: **0.92**
- Classification Report:
  - Control: Precision = 0.89, Recall = 0.94
  - Huntington’s: Precision = 0.89, Recall = 0.91
  - Parkinson’s: Precision = 1.00, Recall = 0.85
  - ALS: Precision = 0.94, Recall = 0.99

## Results
- Random Forest outperformed other models due to:
  - **Class imbalance robustness**  
  - **Ability to handle outliers** with ensemble learning  
- Achieved **92% test accuracy** with balanced precision, recall, and F1-scores across all classes.  

## Conclusion
The project successfully demonstrated that gait dynamics can be used as a **non-invasive biomarker** for classifying neurodegenerative diseases. Random Forest provided the best results, making it a strong candidate for future deployment in clinical decision-support systems.  

## Technologies Used
- Python  
- Pandas, NumPy, Matplotlib, Seaborn  
- scikit-learn  
