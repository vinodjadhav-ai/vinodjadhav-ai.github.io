# Unit 11: Model Performance Measurement

**Module:** Machine Learning  
**Unit:** 11 – Model Selection and Evaluation  
**Activity:** Model Performance Measurement  
**Notebook:** `Unit11_model_Performance_Measurement.ipynb`

## 1. Activity Overview

The objective of this activity is to understand how machine learning models are evaluated using different performance metrics.

The supplied Jupyter notebook introduces classification and regression evaluation methods, including confusion matrices, accuracy, precision, recall, F1 score, ROC-AUC and R².

As part of the activity, I experimented with changing the training and testing split to observe how it affected ROC-AUC results.

## 2. ROC-AUC Experiment: Changing the Test Size

### Objective

To observe how changing the `test_size` parameter affects the ROC-AUC scores of a multiclass classification model.

### Dataset and Model

- **Dataset:** Iris dataset
- **Algorithm:** Support Vector Machine (SVM)
- **Classification approach:** One-vs-Rest (OvR)
- **Kernel:** Linear
- **Random state:** 0
- **Metric:** ROC-AUC

The notebook also added random noise features to make the classification problem more challenging.

### Experiment 1 – Original Configuration

The initial training and testing split was:

```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.5, random_state=0
)
```

Approximately 50% of the dataset was used for training and 50% for testing.

**Observed results:**

| Metric            | ROC-AUC |
| ----------------- | ------: |
| Micro-average AUC |  0.7277 |
| Class 0 AUC       |  0.9127 |
| Class 1 AUC       |  0.6037 |
| Class 2 AUC       |  0.7868 |

### Experiment 2 – Modified Configuration

I changed only the `test_size` parameter from `0.5` to `0.3`, keeping `random_state=0`.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.3, random_state=0
)
```

This allowed approximately 70% of the dataset to be used for training and 30% for testing.

**Observed results:**

| Metric            | ROC-AUC |
| ----------------- | ------: |
| Micro-average AUC |  0.7583 |
| Class 0 AUC       |  0.9526 |
| Class 1 AUC       |  0.6008 |
| Class 2 AUC       |  0.7754 |

## 3. Comparison of Results

| Metric            | Test size = 0.5 | Test size = 0.3 | Observation        |
| ----------------- | --------------: | --------------: | ------------------ |
| Micro-average AUC |          0.7277 |          0.7583 | Increased          |
| Class 0 AUC       |          0.9127 |          0.9526 | Increased          |
| Class 1 AUC       |          0.6037 |          0.6008 | Slightly decreased |
| Class 2 AUC       |          0.7868 |          0.7754 | Slightly decreased |

## 4. Interpretation

I observed that reducing the `test_size` from 0.5 to 0.3 increased the micro-average ROC-AUC from 0.7277 to 0.7583.

Initially, I expected that having more training data would improve the results for all three classes. However, the results were mixed. Class 0 improved, while Classes 1 and 2 decreased slightly.

This helped me understand that a higher overall performance score does not necessarily mean that the model performs better for every individual class.

I also recognised that changing the test size changes both the training data and the test samples. Therefore, this single experiment is not enough to conclude that having more training data caused the improvement.

## 5. Technical Observation

While running the original notebook, I encountered a `FutureWarning` relating to the `probability=True` parameter in scikit-learn's SVM classifier.

Since the ROC-AUC calculation used `decision_function()` rather than `predict_proba()`, I removed the unnecessary `probability=True` parameter and reran the cell successfully.

This also gave me some experience of checking compatibility issues when using an existing notebook with a newer version of a Python library.

## 6. Supporting Evidence

The following screenshots record the actual notebook results:

- `screenshots/auc-test-size-50.png` — ROC-AUC results using `test_size=0.5`.
- `screenshots/auc-test-size-30.png` — ROC-AUC results using `test_size=0.3`.

The executed Jupyter notebook is also retained as part of the activity evidence.

## 7. R² Experiment

## 7. R² and MAE Experiment

### Objective

The objective of this experiment was to understand how changes in predicted values affect two regression evaluation metrics: Mean Absolute Error (MAE) and R-squared (R²).

### Experiment 1 – Original Predictions

I first executed the original example provided in the notebook.

```python
from sklearn.metrics import mean_absolute_error, r2_score

y_true = [3, -0.5, 2, 7]
y_pred = [2.5, 0.0, 2, 8]

print("MAE:", mean_absolute_error(y_true, y_pred))
print("R²:", r2_score(y_true, y_pred))
```

**Observed results:**

- MAE: 0.50
- R²: 0.9486

### Experiment 2 – Modified Predictions

I kept the actual values unchanged and modified two predicted values.

```python
y_true = [3, -0.5, 2, 7]
y_pred = [2.9, 0.0, 1, 8]

print("MAE:", mean_absolute_error(y_true, y_pred))
print("R²:", r2_score(y_true, y_pred))
```

**Observed results:**

- MAE: 0.65
- R²: 0.9226

### Comparison of Results

| Evaluation Metric | Original Predictions | Modified Predictions | Observation |
| ----------------- | -------------------: | -------------------: | ----------- |
| MAE               |                 0.50 |                 0.65 | Increased   |
| R²                |               0.9486 |               0.9226 | Decreased   |

### Interpretation

I observed that changing the predicted values increased the MAE from 0.50 to 0.65, while R² decreased from 0.9486 to 0.9226.

Before doing this exercise, I had only a basic understanding of regression evaluation metrics. This experiment helped me see that MAE and R² measure different aspects of prediction quality.

MAE shows the average size of prediction errors, whereas R² indicates how well the predictions explain the variation in actual values compared with a simple mean-based prediction.

I also learned that a higher R² score is generally preferable, while a lower MAE indicates smaller prediction errors.

These results helped me understand why evaluating regression models using more than one metric can provide a clearer picture of their performance.

## 8. Learning Outcome

**Articulate the legal, social, ethical and professional issues faced by machine learning professionals.**

Completing this activity helped me understand that model evaluation depends on the type of machine learning problem. ROC-AUC is useful for evaluating classification performance, while MAE and R² are used for regression.

Changing the test size showed me that overall classification scores can improve even when individual class results do not. Modifying the regression predictions demonstrated how increasing errors can affect MAE and R².

The main lesson I gained is that selecting and interpreting suitable evaluation metrics is just as important as obtaining a high score. In practical applications, model performance should be examined carefully before relying on predictions.