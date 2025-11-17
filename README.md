# 🌸 Iris Flower Classification — Comparative ML Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue) ![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange) ![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📖 Project Overview

This project performs **Exploratory Data Analysis (EDA)** and **classification** on Fisher's Iris dataset. The goal is to classify iris flowers into three species from four morphological features, and compare multiple supervised learning algorithms.

**Species (Target Mapping)**

| Label | Species         |
| ----- | --------------- |
| 0     | Iris Setosa     |
| 1     | Iris Versicolor |
| 2     | Iris Virginica  |

---

## 📊 Dataset Summary

* **Samples:** 150 (50 per species)
* **Features (cm):** `sepal length`, `sepal width`, `petal length`, `petal width`
* **Target:** `species` (0, 1, 2)

---

## 🔬 Key Findings (short)

* `petal length` and `petal width` are highly correlated (≈ 0.96).
* `Iris Setosa` is linearly separable from the other two classes.
* Petal features are the strongest predictors.

---

## 🛠️ Installation & Requirements

```bash
# Recommended Python >= 3.8
pip install pandas numpy matplotlib seaborn scikit-learn
```

**Libraries used**

* `pandas` — data manipulation
* `numpy` — numerical operations
* `matplotlib`, `seaborn` — visualization
* `scikit-learn` — modeling & evaluation

---

## 🧭 Methodology

### 1. Exploratory Data Analysis (EDA)

* Pairplots to visualize relationships — shows Setosa separability.
* Correlation heatmap — reveals multicollinearity between petal features.
* Basic univariate plots and class counts to verify class balance.

### 2. Preprocessing

* **Label mapping:** Map numeric labels to species names for readability.
* **Train/Test split:** 80% train / 20% test (use a fixed `random_state` for reproducibility).
* **Scaling:** `StandardScaler` to normalize features (important for SVM).

### 3. Models Trained

* **Logistic Regression** (linear baseline)
* **Decision Tree Classifier** (interpretable, rule-based)
* **Support Vector Machine (SVM)** (max-margin geometric classifier)

### 4. Evaluation Metrics

* **Accuracy**
* **Confusion Matrix**
* **Classification Report** (Precision, Recall, F1-score — weighted)

---

## 🧪 Results

All three models achieved **100% accuracy** on the test split used for this analysis.

| Model               | Accuracy | Precision (weighted) | F1-score (weighted) |
| ------------------- | :------: | :------------------: | :-----------------: |
| Logistic Regression |   1.00   |         1.00         |         1.00        |
| Decision Tree       |   1.00   |         1.00         |         1.00        |
| SVM                 |   1.00   |         1.00         |         1.00        |

> **Note:** Perfect scores on the Iris dataset are common because of its small size, cleanliness, and natural separability (especially for Setosa).

---

## 🔍 Analysis of Perfect Scores

Reasons for 100% performance on this dataset (and why to still be cautious):

1. **Small, clean dataset** — no missing values or noisy labels.
2. **Biological separability** — classes are distinct in feature space.
3. **Test split** — with a small test set (e.g., 30 samples), a representative split can easily be perfectly separable.

**Caveat:** In real-world applications, expect noise, class imbalance, and distribution shift — which make perfect accuracy unrealistic. Prefer cross-validation (k-fold) and additional validation strategies to verify generalization.

---

## 💡 Conclusion

All models performed equally well on this dataset; however, **SVM** is often preferred here for its margin-maximizing property, which tends to generalize better to small perturbations and outliers than an unpruned decision tree. Logistic Regression remains a solid, interpretable baseline.

---

## 📂 File Structure

```
├── IRIS.ipynb   # Main notebook (EDA + model training + plots)
├── README.md             # Project documentation (this file)
└── requirements.txt      # Dependencies
```

---

## 🚀 Usage

```bash
# Clone the repository
git clone https://github.com/yourusername/iris-classification.git
cd iris-classification

# Create and activate virtual env (optional)
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Open the notebook
jupyter notebook IRIS_Analysis.ipynb
```

---
## 📚 References

* Fisher, R. A. (1936). *The use of multiple measurements in taxonomic problems.*
* scikit-learn documentation: classification examples and metrics.

---

