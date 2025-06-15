# Predict-Student-Dropout-Risk

| Instance                    | Optimizer | Regularizer | Dropout | Early Stopping | Learning Rate | Accuracy    | F1 Score    | Precision   | Recall      | Loss        |
| --------------------------- | --------- | ----------- | ------- | -------------- | ------------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| **1** – Baseline NN         | Default   | None        | 0.0     | ❌              | Default       | *e.g.* 0.77 | *e.g.* 0.76 | *e.g.* 0.75 | *e.g.* 0.77 | *e.g.* 0.60 |
| **2** – Adam + L2           | Adam      | L2          | 0.3     | ✅              | 0.001         | *e.g.* 0.78 | *e.g.* 0.78 | *e.g.* 0.77 | *e.g.* 0.78 | *e.g.* 0.55 |
| **3** – RMSprop             | RMSprop   | None        | 0.5     | ❌              | 0.0005        | *e.g.* 0.76 | *e.g.* 0.75 | *e.g.* 0.74 | *e.g.* 0.75 | *e.g.* 0.58 |
| **4** – Adam + L1           | Adam      | L1          | 0.2     | ✅              | 0.01          | *e.g.* 0.79 | *e.g.* 0.79 | *e.g.* 0.78 | *e.g.* 0.79 | *e.g.* 0.52 |
| **5** – Logistic Regression | –         | –           | –       | –              | –             | **0.78**    | **0.77**    | **0.77**    | **0.78**    | **–**       |


🔹 Problem Summary (4 lines)
High student dropout rates affect long-term educational success and resource allocation. By analyzing academic performance and behavioral patterns, we can identify at-risk students early. Machine Learning enables automated prediction of dropout likelihood. This project aims to build and compare multiple models to detect dropout risk using real student data.
