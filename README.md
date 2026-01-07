# Predicting Home Loan Eligibility Using Machine Learning
**Group Project – Applied Machine Learning**

## 📌 Project Overview
Home loans are a major revenue driver for financial institutions, but inaccurate approval decisions can significantly increase credit risk and operational cost. Manual loan reviews are often slow, inconsistent, and difficult to scale.

This project applies machine learning techniques to **predict home loan approval eligibility**, helping lenders make faster, more consistent, and data-driven decisions while balancing revenue growth and risk control.

---

## 🎯 Business Objectives
The project is designed to support smarter lending decisions by addressing the following goals:

- Predict whether a loan application should be approved or rejected
- Reduce approval of high-risk applicants
- Minimize rejection of qualified applicants
- Improve consistency and scalability of loan evaluations

---

## 📊 Dataset
- **Size:** ~600 historical loan applications  
- **Target Variable:** `Loan_Status`  
  - `1` = Approved  
  - `0` = Not Approved  

### Key Features
- **Demographics:** Gender, Married, Education, Dependents, Self-Employed  
- **Financials:** ApplicantIncome, CoapplicantIncome, LoanAmount, Loan_Amount_Term  
- **Risk Indicator:** Credit_History  
- **Property Information:** Urban, Semiurban, Rural  

---

## 🧹 Data Preprocessing
Several preprocessing steps were applied to improve data quality and model performance:

- Imputed missing values  
  - Categorical: mode  
  - Numerical: median  
- Removed non-informative identifier (`Loan_ID`)
- One-hot encoded categorical variables
- Binary encoding for selected features (e.g., Married, Self-Employed)
- Feature scaling using `StandardScaler`
- Engineered new features:
  - `Total_Income`
  - `Balance_Income` (disposable income after EMI)
- Removed extreme outliers using Z-score filtering
- Addressed class imbalance using **SMOTE** (applied to training data only)

---

## 🔍 Exploratory Data Analysis
Key insights from EDA include:

- Approval rate is moderately imbalanced (~68% approved, 32% rejected)
- Credit history is the strongest predictor of approval
- Semiurban properties show the highest approval rates
- Income variables are right-skewed with notable outliers
- Approval decisions are driven more by creditworthiness than income alone

---

## 🤖 Models Implemented
Three classification models were trained and evaluated:

### 1️⃣ Logistic Regression (Baseline)
- Chosen for transparency and interpretability
- Balanced precision and recall
- Strong performance identifying qualified applicants
- Odds ratio analysis revealed key approval drivers

### 2️⃣ Decision Tree
- Captures non-linear interactions
- Provides interpretable decision rules
- Showed signs of overfitting
- Useful for understanding key approval factors

### 3️⃣ Random Forest (Final Model)
- Ensemble approach for robust prediction
- Best overall performance on unseen data
- Strong ability to correctly approve safe applicants
- Balanced trade-off between risk detection and approval accuracy

---

## 📈 Model Evaluation
Evaluation metrics included:
- Accuracy
- Precision
- Recall
- F1-score
- ROC–AUC
- 5-fold Cross-Validation

### Performance Summary
- **Random Forest achieved the highest ROC–AUC and overall accuracy**
- Logistic Regression provided the best interpretability
- Decision Tree offered insight into decision logic but weaker generalization

---

## 💡 Key Insights
- **Credit History is the dominant approval driver**
- Applicants with strong financial stability indicators are more likely to be approved
- Semiurban properties show higher approval likelihood
- Ensemble models outperform single models in stability and accuracy
- Balancing risk detection and approval rate is essential for lending strategy

---

## 🧠 Business Recommendations
- Prioritize credit history as a core approval criterion
- Use ensemble models to support automated loan screening
- Maintain transparency with interpretable models for compliance
- Monitor model bias and retrain periodically
- Expand feature set with additional financial and employment data

---

## 🧪 Tools & Technologies
- Python
- Pandas, NumPy
- Scikit-learn
- SMOTE
- Matplotlib / Seaborn
- Jupyter Notebook
