# Predict-Student-Dropout-Risk

| Instance                    | Optimizer | Regularizer | Dropout | Early Stopping | Learning Rate | Accuracy    | F1 Score    | Precision   | Recall      | Loss        |
| --------------------------- | --------- | ----------- | ------- | -------------- | ------------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| **1** – Baseline NN         | Default   | None        | 0.0     | ❌              | Default       | *e.g.* 0.77 | *e.g.* 0.76 | *e.g.* 0.75 | *e.g.* 0.77 | *e.g.* 0.60 |
| **2** – Adam + L2           | Adam      | L2          | 0.3     | ✅              | 0.001         | *e.g.* 0.78 | *e.g.* 0.78 | *e.g.* 0.77 | *e.g.* 0.78 | *e.g.* 0.55 |
| **3** – RMSprop             | RMSprop   | None        | 0.5     | ❌              | 0.0005        | *e.g.* 0.76 | *e.g.* 0.75 | *e.g.* 0.74 | *e.g.* 0.75 | *e.g.* 0.58 |
| **4** – Adam + L1           | Adam      | L1          | 0.2     | ✅              | 0.01          | *e.g.* 0.79 | *e.g.* 0.79 | *e.g.* 0.78 | *e.g.* 0.79 | *e.g.* 0.52 |
| **5** – Logistic Regression | –         | –           | –       | –              | –             | **0.78**    | **0.77**    | **0.77**    | **0.78**    | **–**       |
