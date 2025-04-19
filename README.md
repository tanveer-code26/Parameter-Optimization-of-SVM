# 🔬 SVM Parameter Optimization

## 📊 Project Summary
This project showcases a systematic approach to optimizing Support Vector Machine (SVM) parameters for a **multi-class classification** task on the [Adult Census Income dataset](https://archive.ics.uci.edu/ml/datasets/adult) from the UCI Machine Learning Repository.

The dataset includes **32,561 rows** and **15 features**, covering demographic and employment-related attributes such as:
- Age
- Education Level
- Marital Status
- Occupation
- Income Bracket (>50K or <=50K)

---

## ⚙️ Data Preprocessing Pipeline
Before model training, the dataset was cleaned and transformed using the following steps:

1. **Missing Value Handling**: All entries containing '?' were replaced with the most frequent (mode) value of their respective column.
2. **Categorical Encoding**: All categorical features were one-hot encoded.
3. **Numerical Scaling**: StandardScaler from `scikit-learn` was used to normalize numerical columns.

---

## 🎓 Model Training & Optimization
- The dataset was split into **70% training** and **30% testing** sets.
- A **multi-class SVM classifier** was trained using random combinations of:
  - **C** (regularization parameter)
  - **Gamma** (kernel coefficient)
  - **Kernel** types: `linear`, `poly`, `rbf`, etc.
- This process was repeated over **10 different samples** of the dataset.
- For each sample, the best parameters and accuracy were recorded.

### Optimization Configuration:
- **Iterations**: 1000
- **Parameter Range**:
  - `C` and `gamma`: Random values between 0 and 1
  - `Kernels`: Linear, Poly, RBF

---

## 📊 Results Summary
The table below displays the best results for each sample:

| Sample | Accuracy | C Value | Gamma Value | Kernel Type |
|--------|----------|---------|--------------|-------------|
| 1      | 0.7798   | 0.6215  | 0.1837       | rbf         |
| 2      | 0.8003   | 0.7293  | 0.6811       | poly        |
| 3      | 0.7977   | 0.7289  | 0.4610       | poly        |
| 4      | 0.7822   | 0.0531  | 0.1680       | rbf         |
| 5      | **0.8027**   | 0.2600  | 0.2012       | poly        |
| 6      | 0.7986   | 0.4441  | 0.5682       | poly        |
| 7      | 0.7934   | 0.3606  | 0.1258       | poly        |
| 8      | 0.7950   | 0.8705  | 0.9408       | poly        |
| 9      | 0.7906   | 0.6741  | 0.0391       | rbf         |
| 10     | 0.7941   | 0.0856  | 0.1096       | rbf         |

🏆 **Best Result**: Sample 5 with an accuracy of **0.8027** using the `poly` kernel.

---

## 🚀 Conclusion
Multi-class SVM can be a powerful tool for classification tasks, especially when applied to preprocessed datasets. By optimizing the SVM parameters, we can achieve high accuracy on the test set. However, proper cross-validation is essential to avoid overfitting, especially when using complex kernels like `poly` and `rbf`.

---

## 📖 References
- UCI Adult Income Dataset: https://archive.ics.uci.edu/ml/datasets/adult
- scikit-learn Documentation: https://scikit-learn.org/stable/
