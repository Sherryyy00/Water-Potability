# 🚰 Water Potability Prediction using Machine Learning

## 📌 Project Overview
This project predicts whether water is **safe (potable)** or **unsafe** for drinking, using physicochemical features.  
The dataset consists of 3,276 water samples with 9 features (e.g., pH, hardness, solids, sulfate).

---

## 🔑 Problem
Clean drinking water is essential for health. Laboratory testing is reliable but costly and time-consuming.  
This project aims to build a **data-driven screening tool** for water safety classification.

---

## 🧾 Dataset
- Source: (https://www.kaggle.com/datasets/adityakadiwal/water-potability)) (Water Potability dataset)  
- Features:
  - `ph`
  - `Hardness`
  - `Solids`
  - `Chloramines`
  - `Sulfate`
  - `Conductivity`
  - `Organic_carbon`
  - `Trihalomethanes`
  - `Turbidity`
- Target:
  - `Potability` (1 = drinkable, 0 = not drinkable)

---

## ⚙️ Workflow / Pipeline
1. Data cleaning & handling missing values
2. Outlier detection & mitigation
3. Feature engineering (pH categories)
4. Train-test split
5. **No leakage**: scaling applied to train only
6. **SMOTE**: handle class imbalance on train set
7. Train models separately:
   - Logistic Regression
   - Support Vector Machine
   - Decision Tree
   - Random Forest
   - XGBoost
8. Model evaluation with accuracy, precision, recall, F1, ROC-AUC
9. Feature importance & SHAP interpretability

---

## 📊 Results
| Model                | Accuracy | Precision | Recall | F1 Score |
|-----------------------|----------|-----------|--------|----------|
| Logistic Regression   | 0.50     | 0.40      | 0.56   | 0.47     |
| SVM                   | 0.62     | 0.52      | 0.44   | 0.48     |
| Decision Tree         | 0.71     | 0.62      | 0.64   | 0.63     |
| Random Forest         | **0.75** | **0.69**  | **0.63** | **0.66** |
| XGBoost               | 0.73     | 0.68      | 0.61   | 0.64     |

➡️ **Random Forest achieved the best balance (F1 = 0.66, AUC ≈ 0.74)**.

---

## 🔍 Key Insights
- Safe water is more likely when pH is between **6.5–8.5 (WHO standard)**, but pH alone is not sufficient.  
- **Sulfate, Solids, and Conductivity** were strong predictors in feature importance analysis.  
- No single feature separates safe vs. unsafe water → **ML models are necessary**.  
- Random Forest + XGBoost both performed strongly; RF slightly better on recall and F1.

---

## 📈 Visuals
- Confusion matrix
- ROC curve
- Feature importance (Random Forest)
- Model performance comparison chart

---

## 🚀 How to Run
```bash
git clone https://github.com/sherryyy00/water-potability-ml.git
cd water-potability-ml

## 🏆 Conclusion
- Random Forest was the best performing model (F1 = 0.66).
- While this tool is not a replacement for laboratory testing, it provides a fast, low-cost, first-pass screening for water safety assessment.
pip install -r requirements.txt
jupyter notebook Water_Prediction.ipynb
