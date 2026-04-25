# income_ai_project
## 3. Modeling and Hyperparameter Tuning

### Model 1: Logistic Regression
I chose Logistic Regression as the primary classifier. To optimize the model, I experimented with the **'C' parameter** (the inverse of regularization strength) to observe its impact on performance.

#### **Experimentation Results:**
| Hyperparameter (C) | Overall Accuracy | Precision (Class 1) | Recall (Class 1) |
| :--- | :--- | :--- | :--- |
| **C = 0.01 (Strong Reg)** | 83.84% | **0.72** | 0.52 |
| **C = 1.0 (Default)** | 83.84% | 0.70 | 0.56 |
| **C = 100 (Weak Reg)** | 83.82% | 0.69 | 0.56 |

#### **Analysis of Hyperparameters:**
* **Strong Regularization ($C=0.01$):** Improved the **Precision to 0.72**. This means the model became more reliable when predicting high-income individuals, although it became more conservative (lower recall).
* **Weak Regularization ($C=100$):** The model became more aggressive in its predictions, which slightly decreased precision and increased the number of **False Positives (957)**.
* **Impact:** The experimentation showed that a smaller 'C' value helps in achieving more reliable predictions for the high-income class by reducing potential overfitting.

---

## 4. Data Visualization & Analysis
Based on the feature coefficients from the Logistic Regression model, the following key factors were identified:

* **Education-num:** Had a strong positive correlation with income, meaning higher education levels significantly increase the probability of earning >50K.
* **Age:** Also showed a positive trend, as older individuals generally have more work experience and higher salaries.
* **Capital-gain:** Identified as a major factor in predicting high-income individuals.

---

## 5. Conclusion
The Logistic Regression model performed consistently with an accuracy of approximately **84%**. Through hyperparameter tuning, I found that adjusting the regularization strength (**C**) allows for a strategic trade-off between precision and recall. For this specific dataset, a balanced 'C' provides a robust model capable of identifying high-income individuals while maintaining high overall accuracy.
