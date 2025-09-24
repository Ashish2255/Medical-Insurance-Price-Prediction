# Medical Insurance Price Prediction  

---

## 📌 Project Overview  
This project focuses on predicting **medical insurance charges** based on demographic and lifestyle factors such as age, sex, BMI, number of children, smoking status, and region. The goal is to analyze feature importance, preprocess the dataset, and compare different machine learning models for prediction accuracy.  

---

## 📊 Dataset  
- **Features**:  
  - `age` (int): Age of the individual  
  - `sex` (categorical): Gender  
  - `bmi` (float): Body Mass Index  
  - `children` (int): Number of children  
  - `smoker` (categorical): Smoking status  
  - `region` (categorical): Residential region  
- **Target**:  
  - `charges` (float): Insurance premium charges  

- **Observations**:  
  - No missing or null values.  
  - Balanced distribution across `sex` and `region`.  
  - Imbalanced distribution in `smoker` (~80:20 ratio).  
  - Most influential features: **age, BMI, smoker**.  

---

## ⚙️ Preprocessing Steps  
- Encoding categorical variables (`sex`, `smoker`, `region`).  
- Outlier handling for BMI and charges.  
- Feature scaling.  
- Exploratory Data Analysis (EDA): correlation matrix, plots, distributions.  

---

## 🧠 Models Implemented  

### 1. Linear Regression with Polynomial Features (with L2 Regularization)  
- Added polynomial features (degree 2 and 3).  
- Achieved **R² score = 0.81**.  
- Limitations: struggled with categorical features and high-dimensionality.  
- Possible overfitting, performance plateaued after multiple epochs.  

---

### 2. Random Forest Regressor  
- Ensemble bagging technique using multiple decision trees.  
- Applied **GridSearchCV** for hyperparameter tuning.  
- Cross-validation used to reduce variance and overfitting.  
- Achieved **R² score = 0.88 (test)** and **0.84 (cross-validation)**.  
- Best performing model in this project.  

---

### 3. XGBoost Regressor (Implemented from Scratch)  
- Boosting technique using gradient descent on error.  
- Regularization applied to improve generalization.  
- Achieved **R² score = 0.878**.  
- Slightly lower than Random Forest due to:  
  - Lack of optimized **DMatrix** structure (used in official XGBoost).  
  - Limited hyperparameter tuning.  
- Potential improvements: reimplement with official XGBoost API for efficiency.    

---

## 📈 Results Summary  

| Model | Test R² Score |
|-------|--------------|
| Linear Regression (Poly+L2) | 0.81 |
| Random Forest Regressor | 0.88 |
| XGBoost Regressor | 0.878 |
---
