
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

| Instance | Optimizer | Regularizer | Dropout | Early Stopping | Learning Rate | Accuracy | F1 Score | Precision | Recall | Notes |
|----------|-----------|-------------|---------|----------------|----------------|----------|----------|-----------|--------|-------|
| **1** – Baseline NN | Adam | None | 0.0 | ❌ | Default | 0.7590 | 0.76 | 0.76 | 0.76 | No optimization |
| **2** – Adam + L2 | Adam | L2 | 0.3 | ✅ | 0.001 | **0.7937** | **0.78** | **0.78** | **0.79** | Best performance |
| **3** – RMSprop | RMSprop | None | 0.5 | ❌ | 0.0005 | 0.7846 | 0.78 | 0.78 | 0.78 | Solid alternative |
| **4** – Adam + L1 | Adam | L1 | 0.2 | ✅ | 0.01 | 0.7530 | 0.69 | 0.67 | 0.75 | Weak Enrolled recall |
| **5** – Logistic Regression | – | – | – | – | – | 0.7800 | 0.77 | 0.77 | 0.78 | Classical ML baseline |

> 📌 *Metrics are based on weighted averages from the classification reports. All models were evaluated on the same test set.*

---

## 📊 Summary & Analysis

### 🥇 Best Performing Neural Network
The most effective model was **Instance 2**, which used:
- Adam optimizer
- L2 regularization
- Dropout (0.3)
- EarlyStopping

It achieved **79.4% accuracy** with excellent performance across all target classes, including a significant boost in the often-challenging "Enrolled" class.

### 🤖 Classical ML Comparison
Logistic Regression (Model 5) performed nearly as well, achieving **78% accuracy**, but like other models, it struggled to identify enrolled students accurately. Neural Networks, especially the optimized ones, provided better class balance and prediction consistency.

---

## 🏁 How to Run the Notebook

1. Upload the dataset to your Google Drive.
2. Open the `notebook.ipynb` in **Google Colab**.
3. Run all cells. Models will be trained and saved in:  
   `/content/drive/MyDrive/saved_models/`
4. To make predictions from the best saved model, run:

```python
from tensorflow.keras.models import load_model

# Load the best model
model = load_model('/content/drive/MyDrive/saved_models/model_2_adam_l2_dropout03_es.keras')

# Predict
preds = model.predict(X_test)
labels = np.argmax(preds, axis=1)
