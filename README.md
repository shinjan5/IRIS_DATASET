# 🌸 Iris Flower Classification

An end-to-end machine learning workflow on the **Iris dataset** — including **Exploratory Data Analysis (EDA)**, **Model Training**, and **Evaluation**.

---

## 📌 Overview
The Iris dataset contains 150 samples of iris flowers across three species:
- *Setosa*
- *Versicolor*
- *Virginica*

Each sample has four features:
- `sepal_length`
- `sepal_width`
- `petal_length`
- `petal_width`

The goal is to classify flowers into their correct species.

**Key Insight from EDA**  
🌿 Petal features (`petal_length`, `petal_width`) show the clearest separation between classes, while sepal features overlap more.

---

## 📂 Project Structure
- **Exploratory Data Analysis (EDA)** — histograms, pairplots, and distribution checks.
- **Model Training** — multiple ML algorithms tested.
- **Evaluation** — accuracy, confusion matrix, and classification report.

---

## 🤖 Algorithms & Cross-Validation Results
Mean accuracy ± standard deviation across folds:

| Model | Accuracy | Std. Dev |
|-------|----------|----------|
| Logistic Regression (LR) | 94.17% | ±6.59% |
| Linear Discriminant Analysis (LDA) | **97.50%** | ±3.82% |
| K-Nearest Neighbors (KNN) | 95.83% | ±4.17% |
| Decision Tree (CART) | 94.17% | ±5.34% |
| Naive Bayes (NB) | 95.00% | ±5.53% |
| Support Vector Machine (SVM) | **98.33%** | ±3.33% |

**📊 Takeaway**:  
- **SVM** achieved the highest accuracy with low variance.  
- **LDA** performed nearly as well, with great consistency.  

---

## 📈 Sample Validation Metrics (SVM)



