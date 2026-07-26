# Codveda Technologies — Machine Learning Internship

Portfolio of machine learning projects completed during the Codveda Technologies ML Internship. Each task follows a consistent notebook structure — data loading, EDA, preprocessing, model training, evaluation, and a conclusion grounded in the actual computed results — and is organized under a shared Google Drive workspace for reproducibility.

**Author:** Lady
**Environment:** Google Colab
**Core stack:** pandas, numpy, scikit-learn, TensorFlow/Keras, matplotlib, seaborn, scipy

---

## Project Structure
Each task folder contains its own `charts/`, `tables/`, and `model/` subfolders holding all saved visualizations, intermediate tables, and trained model artifacts.

---

## Completed Tasks

### Level 1 — Foundations of Machine Learning

**Task 2: Linear Regression — Boston Housing Price Prediction**
Simple linear regression predicting median house value (MEDV) from a single predictor. LSTAT (% lower status population) was selected automatically as the strongest correlated feature.
- Regression equation: `MEDV = 35.3473 + (-0.9925 × LSTAT)`
- R² Score: **0.4997** | MAE: 4.1365 | RMSE: 5.2798

**Task 3: KNN — Customer Churn Prediction**
K-Nearest Neighbors classifier on telecom customer data, tuned across 11 values of K.
- Best K: **5** | Test Accuracy: **90.70%**
- Precision: 0.8235 | Recall: 0.4421 | F1-score: 0.5753
- 605/667 test customers correctly classified

### Level 2 — Classification & Clustering

**Task 2: Decision Tree — Iris Species Classification**
Decision tree classifier with pruning applied to reduce overfitting.
- Initial tree: depth 5, 93.33% test accuracy (100% train — overfit)
- Pruned tree: depth 3, **96.67% test accuracy**, 98.29% train accuracy
- Most important feature: petal_length (66.1% importance)

**Task 3: K-Means Clustering — Telecom Customer Segmentation**
Unsupervised segmentation of telecom customers by usage and plan behavior (churn label withheld from training).
- Optimal clusters (Elbow Method): **4**
- Cluster sizes: 845 / 270 / 893 / 658
- PCA (2D) variance explained: 23.70%
- Final inertia: 26,149.77
- Key insight: churn was not driven by usage volume — the international-plan cluster showed disproportionately higher churn

### Level 3 — Advanced Models

**Task 2: SVM — Binary Sentiment Analysis**
Linear vs. RBF kernel SVM comparison on TF-IDF features from social media text, mapped from 190+ raw emotion labels down to Positive/Negative.
- Linear SVM: **92.0% accuracy**, F1: 0.947, AUC: 0.985
- RBF SVM: 80.8% accuracy, F1: 0.883, AUC: 0.984
- Linear kernel outperformed RBF by ~11.2% accuracy — consistent with linear kernels suiting high-dimensional sparse TF-IDF data
- PCA note: 2D projection captured only 1.9% of variance (visualization is illustrative only)

**Task 3: Neural Network — MNIST Digit Classification**
Feed-forward neural network (TensorFlow/Keras) with two ReLU hidden layers, Dropout regularization, and softmax output.
- Test Accuracy: **97.91%** | Test Loss: 0.0751
- Train/validation accuracy gap: 0.39% (no overfitting)
- Misclassified: 209 / 10,000 test images — mostly visually similar digit pairs (e.g., 4/9, 3/5)

---

## Summary of Results

| Level | Task | Algorithm | Dataset | Key Metric |
|---|---|---|---|---|
| 1 | 2 | Linear Regression | Boston Housing | R² = 0.4997 |
| 1 | 3 | KNN | Telecom Churn | Accuracy = 90.70% |
| 2 | 2 | Decision Tree | Iris | Accuracy = 96.67% |
| 2 | 3 | K-Means | Telecom Churn | 4 clusters, Inertia = 26,149.77 |
| 3 | 2 | SVM (Linear) | Sentiment (Social Media) | Accuracy = 92.0%, AUC = 0.985 |
| 3 | 3 | Neural Network | MNIST | Accuracy = 97.91% |

---

## Notes

- All datasets, charts, tables, and trained models are stored in a shared Google Drive workspace (`/Codveda_Internship/`), organized by task.
- Every conclusion in each notebook is generated from the model's actual computed metrics — no placeholder or assumed values.
- Package installs use upgrade-only pip commands to stay compatible with Colab's preinstalled environment.
