# MSCS_634 Project Deliverable 1

## Dataset Summary
For this project, I used the **Heart Disease Dataset**, which contains 303 records and 14 attributes. The dataset includes both numerical and categorical features:

- **Age**: Age of the individual.  
- **Sex**: Gender (1 = male, 0 = female).  
- **Chest Pain Type (cp)**: Type of chest pain experienced.  
- **Resting Blood Pressure (trestbps)**: Blood pressure during rest (mm Hg).  
- **Cholesterol (chol)**: Serum cholesterol level (mg/dl).  
- **Fasting Blood Sugar (fbs)**: Whether fasting blood sugar is greater than 120 mg/dl.  
- **Resting Electrocardiographic Results (restecg)**: Electrocardiographic results.  
- **Maximum Heart Rate Achieved (thalach)**: Highest heart rate achieved during exercise.  
- **Exercise Induced Angina (exang)**: Whether exercise induced angina was experienced.  
- **Oldpeak**: Depression induced by exercise relative to rest.  
- **Slope**: Slope of the peak exercise ST segment.  
- **Number of Vessels Colored by Fluoroscopy (ca)**: Count of colored vessels.  
- **Thalassemia (thal)**: Categorical feature indicating presence of thalassemia.  
- **Target**: Whether the individual has heart disease (1 = yes, 0 = no).  

I chose this dataset because predicting heart disease is a significant healthcare challenge, and the dataset provides a balanced mix of features suitable for classification.

---

## Key Insights from EDA
1. **Cholesterol Distribution**  
   The distribution of cholesterol levels was right‐skewed, suggesting a **log transformation** may help normalize the data.

2. **Age vs. Maximum Heart Rate**  
   There is a moderate negative correlation between age and maximum heart rate achieved, indicating older individuals tend to reach lower peak heart rates during exercise.

3. **Target Balance**  
   The target variable shows a mild class imbalance (slightly more cases with heart disease), but overall remains sufficient for modeling without drastic resampling.

4. **Outliers in Cholesterol**  
   Significant outliers exist in the cholesterol feature. These were addressed via the **Interquartile Range (IQR) method** to improve data quality.

---

## Major Steps in Data Cleaning & Exploration

1. **Handling Missing Values**  
   - Identified missing entries in several columns.  
   - Imputed numerical missing values with the **column mean** to preserve dataset size.

2. **Removing Duplicates**  
   - Checked for and removed duplicate rows to prevent skewed analysis.

3. **Outlier Detection & Removal**  
   - Used **boxplots** to detect outliers, particularly in the `chol` feature.  
   - Removed extreme values beyond 1.5 × IQR to reduce their influence.

4. **Ensuring Correct Data Types**  
   - Converted categorical features (`sex`, `cp`, `fbs`, `restecg`, `exang`, `slope`, `ca`, `thal`) to appropriate data types.  
   - Verified all columns had the intended type to avoid downstream errors.

---

## Challenges & Solutions

- **Missing Data Strategy**  
  - *Challenge:* Deciding between row deletion vs. imputation.  
  - *Solution:* Chose mean‐imputation to retain maximum records without introducing bias.

- **Outlier Treatment**  
  - *Challenge:* Whether to remove extreme values or transform.  
  - *Solution:* After visual exploration, removed extreme outliers using the IQR method to simplify modeling.

- **Feature Scaling Considerations**  
  - *Challenge:* Determining if and when to scale features.  
  - *Solution:* Deferred scaling to the modeling phase; noted that features like `chol` and `trestbps` may benefit from normalization or standardization in the next step.

---

## Conclusion & Next Steps
This deliverable covered **data cleaning** and **exploratory data analysis (EDA)**. The dataset is now free of duplicates and extreme outliers, missing values have been handled, and basic insights have been extracted. In the next phase, I will:

1. Engineer additional features (e.g., binning age, creating interaction terms).  
2. Apply feature scaling and transformations where necessary.  
3. Build, tune, and evaluate classification models (e.g., logistic regression, random forest, XGBoost) to predict heart disease presence.

---
