# Alphabet Soup Deep Learning Model Report

## **Overview of the Analysis**
The purpose of this analysis is to develop a deep learning model that predicts whether an Alphabet Soup-funded organization will be successful. The goal was to optimize the model to achieve an accuracy of at least 75%.

---

## **Results**

### **Data Preprocessing**
- **Target Variable:** `IS_SUCCESSFUL`
- **Feature Variables:** Categorical (`APPLICATION_TYPE`, `AFFILIATION`, etc.), Numerical (`ASK_AMT`).
- **Removed Variables:** `EIN`, `NAME` (IDs that do not contribute to predictions).

---

### **Model 1 - Baseline Model**
- **Architecture:**
  - Input Features: 86
  - Hidden Layers: 86 → 43 → 1
  - Activation: **ReLU (Hidden Layers), Sigmoid (Output Layer)**
- **Performance:**
  - **Test Accuracy:** 73.06%
  - **Loss:** 0.5631

#### **Model 1 Summary**
![Model 1 Summary](models/model%201.png)

#### **Model 1 Accuracy**
![Model 1 Accuracy](models/model%201%20accuracy.png)

---

### **Model 2 - Increased Complexity & Dropout**
- **Changes from Model 1:**
  - More neurons (**128 → 64 → 20 → 1**).
  - Added **Dropout Layers**.
  - Used **LeakyReLU Activation**.

- **Performance:**
  - **Test Accuracy:** 39.91%
  - **Loss:** 0.8462
  - **Observation:** Overfitting occurred, leading to poor generalization.

#### **Model 2 Summary**
![Model 2 Summary](models/model%202.png)

#### **Model 2 Accuracy**
![Model 2 Accuracy](models/model%202%20accuracy.png)

---

### **Model 3 - L2 Regularization & Dropout Reduction**
- **Changes from Model 2:**
  - **L2 Regularization Applied**.
  - **Dropout Reduced**.
  - Adjusted neuron sizes (**64 → 40 → 15 → 1**).

- **Performance:**
  - **Test Accuracy:** 53.43%
  - **Loss:** 0.6910
  - **Observation:** Model was more stable but did not achieve the target accuracy.

#### **Model 3 Summary**
![Model 3 Summary](models/model%203.png)

#### **Model 3 Accuracy**
![Model 3 Accuracy](models/model%203%20accuracy.png)

---

### **Steps Taken to Improve Performance**
1. **Increased model complexity** (More neurons and layers in Model 2).
2. **Implemented dropout** (Regularization to prevent overfitting in Model 2).
3. **Added L2 regularization and fine-tuned dropout** (Model 3 stabilized training but did not significantly improve accuracy).

---

### **Summary & Recommendations**
- **Final Accuracy:** The highest accuracy achieved was **73.06%** with Model 1.
- **Challenges:** Increasing model complexity did not improve accuracy, and overfitting was an issue.
- **Alternative Approach:**
  - **Random Forest or XGBoost** may perform better for tabular data.
  - Feature engineering, such as **creating interaction terms or binning**, could improve the dataset.
  - Hyperparameter tuning using **GridSearchCV** or **Bayesian Optimization** could refine the deep learning model.

🚀 **Conclusion:** The deep learning approach showed promise but did not reach 75% accuracy. Alternative models should be explored for better performance.



