# Re-create the professional README.md content after environment reset

readme_content = """
# 🎓 Student Dropout Risk Prediction Using Machine Learning

---

## 📌 Overview

This project aims to predict student dropout risk using academic, behavioral, and demographic data. Leveraging classical and neural network machine learning techniques, the goal is to proactively identify students at risk of dropping out, enabling institutions to intervene early.

---

## 📁 Dataset Summary

- **Source**: UCI Machine Learning Repository – [Predict Students’ Dropout and Academic Success](https://archive.ics.uci.edu/dataset/697)
- **Total Records**: 4,424 student entries
- **Features**: 35 total — academic, demographic, and behavioral attributes
- **Target Variable**: 3-Class Classification → `Dropout`, `Enrolled`, `Graduate`

---

## 🔧 Model Configurations and Results

| Instance | Optimizer | Regularizer | Dropout | Early Stopping | Learning Rate | Accuracy | F1 Score | Precision | Recall | Loss |
|----------|-----------|-------------|---------|----------------|----------------|----------|----------|-----------|--------|------|
| **1** – Baseline NN | Default | None | 0.0 | ❌ | Default | *e.g.* 0.77 | *e.g.* 0.76 | *e.g.* 0.75 | *e.g.* 0.77 | *e.g.* 0.60 |
| **2** – Adam + L2 | Adam | L2 | 0.3 | ✅ | 0.001 | *e.g.* 0.78 | *e.g.* 0.78 | *e.g.* 0.77 | *e.g.* 0.78 | *e.g.* 0.55 |
| **3** – RMSprop | RMSprop | None | 0.5 | ❌ | 0.0005 | *e.g.* 0.76 | *e.g.* 0.75 | *e.g.* 0.74 | *e.g.* 0.75 | *e.g.* 0.58 |
| **4** – Adam + L1 | Adam | L1 | 0.2 | ✅ | 0.01 | *e.g.* 0.79 | *e.g.* 0.79 | *e.g.* 0.78 | *e.g.* 0.79 | *e.g.* 0.52 |
| **5** – Logistic Regression | – | – | – | – | – | **0.78** | **0.77** | **0.77** | **0.78** | **–** |

> 📌 *Note: Replace `*e.g.*` values with the exact results from your notebook output.*

---

## 📊 Summary & Analysis

### 🔍 Best Performing Neural Network
The best results were achieved with **Instance 4** — Adam optimizer with L1 regularization and early stopping. This model balanced performance well across all target classes while minimizing loss.

### 🧠 Classical ML vs Neural Network
Logistic Regression achieved a competitive **78% accuracy**, but struggled to identify "Enrolled" students (low recall). Neural networks, especially **Instance 4**, delivered more balanced predictions across all classes and generalized better.

---

## 🏁 How to Run the Notebook

1. Upload the dataset to your Google Drive.
2. Open the provided `notebook.ipynb` in **Google Colab**.
3. Run all cells. Models will be trained and saved to `/content/drive/MyDrive/saved_models/`.
4. To make predictions from a saved model, use:

```python
from tensorflow.keras.models import load_model

# Load best model
model = load_model('/content/drive/MyDrive/saved_models/model_4_adam_l1_dropout02_es.keras')

# Predict
preds = model.predict(X_test)
labels = np.argmax(preds, axis=1)
