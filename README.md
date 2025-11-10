# Assignment8 

By:Abhishek Kumar DA25C002


# 🚴‍♂️ Bike Sharing Demand Prediction using Ensemble Learning

This project predicts **hourly bike rental demand** based on weather and temporal features using various **machine learning and ensemble techniques**.  
The study demonstrates how combining models can improve prediction accuracy through **bias–variance optimization** and **model diversity**.

---

## 📘 Project Overview
DATASET LINK : https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset
The goal of this project is to analyze the **Bike Sharing dataset** and build regression models that can accurately predict the **total count of bike rentals (`cnt`)** for a given hour.  

The project progresses through multiple stages:
1. **Data Preprocessing & Feature Engineering**
2. **Baseline Model Creation**
3. **Ensemble Learning (Bagging, Boosting, Stacking)**
4. **Model Comparison & Evaluation**

---

## 🧹 Part A: Data Preprocessing and Baseline

### Tasks:
- Loaded the dataset and removed irrelevant columns such as `instant`, `dteday`, `casual`, and `registered`.
- Applied **One-Hot Encoding** on categorical variables like `season`, `weathersit`, `mnth`, and `hr`.
- Split the dataset into training and testing sets using an **80–20 split**.
- Built baseline models:
  - **Linear Regression**
  - **Decision Tree Regressor (max_depth=6)**

📊 **Baseline RMSE (Decision Tree):** 122.03

---

## 🌲 Part B: Ensemble Techniques for Bias and Variance Reduction

### **1. Bagging Regressor**
- Implemented Bagging with a Decision Tree as the base estimator.
- Reduced model variance through sampling with replacement.
- **RMSE:** 82.58  
- **Improvement:** +32.33% over baseline

### **2. Gradient Boosting Regressor**
- Used Gradient Boosting to sequentially correct prediction errors and reduce bias.
- **RMSE:** 79.65  
- **Improvement:** +34.73% over baseline

---

## 🤖 Part C: Stacking Regressor for Optimal Performance

- Implemented a **Stacking Regressor** combining:
  - **Base Learners:** KNN Regressor, Bagging Regressor, Gradient Boosting Regressor  
  - **Meta-Learner:** Ridge Regression
- The meta-learner learned how to optimally combine predictions from all base models.
- **RMSE:** 71.67  
- **Improvement:** +41.27% over baseline

---

## 📊 Part D: Final Model Comparison

| Model | RMSE | Improvement vs Baseline (%) |
|:--|:--:|:--:|
| Decision Tree | 122.03 | 0.00 |
| Bagging Regressor | 82.58 | 32.33 |
| Gradient Boosting Regressor | 79.65 | 34.73 |
| Stacking (Ridge Meta-Learner) | **71.67** | **41.27** |

✅ **Best Model:** *Stacking Regressor (Ridge Meta-Learner)*

---

## 💡 Key Insights

- **Bagging** effectively reduced variance by combining multiple Decision Trees trained on bootstrapped samples.  
- **Gradient Boosting** reduced bias by focusing on correcting the errors of previous learners.  
- **Stacking** delivered the best results by blending multiple diverse models and learning how to combine them optimally.

---

## 📈 Visualizations

- Distribution of weather-related features (`temp`, `atemp`, `hum`, `windspeed`)
- Hourly rental trends for working vs non-working days
- Actual vs Predicted Bike Rentals (Stacking Model)
- Residuals vs Predicted Values

These visualizations helped validate model performance and interpret prediction accuracy.

---

## 🧩 Technologies Used

- **Python**
- **Pandas**, **NumPy**
- **Scikit-learn**
- **Matplotlib**, **Seaborn**
- **Jupyter Notebook**

---

## 🏁 Conclusion

The project demonstrates how ensemble learning techniques — Bagging, Boosting, and Stacking — can significantly improve predictive accuracy in regression problems.  
The **Stacking Regressor with Ridge Meta-Learner** achieved the **lowest RMSE (71.67)**, outperforming all other models by over **41%**, thanks to its ability to combine diverse model strengths and balance the bias–variance trade-off effectively.
