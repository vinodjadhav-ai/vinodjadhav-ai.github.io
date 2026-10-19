# Unit 3: Correlation and Regression — Completed Activity

**Module:** Machine Learning  
**Unit:** 3  
**Activity:** Run four Jupyter Notebook programmes and change values to observe the effects on correlation and regression.

## 1. Activity overview

I ran the four supplied exercises covering Pearson correlation, simple linear regression, multiple linear regression and polynomial regression. For each exercise, I first checked the original results and then changed a value or input to see how the result responded. I kept screenshots of the before-and-after outputs rather than relying only on the written observations below.

## 2. Exercise 1 — Covariance and Pearson correlation

**Change:** I increased the random-noise multiplier in the second variable from `10` to `30`, keeping `seed(1)` and the rest of the calculation unchanged.

```python
# Original
data2 = data1 + (10 * randn(1000) + 50)

# Modified
data2 = data1 + (30 * randn(1000) + 50)
```

| Measure             | Original (noise = 10) | Modified (noise = 30) |
| ------------------- | --------------------: | --------------------: |
| Covariance          |               389.755 |               398.598 |
| Pearson correlation |                 0.888 |                 0.549 |

**Observation:** Pearson correlation fell from 0.888 to 0.549, so the positive linear relationship became less pronounced as the amount of random variation increased. Covariance stayed positive and changed slightly upwards; unlike correlation, its size depends on the measurement scales. The exercise helped me see why correlation is easier to compare when I want to describe the *strength* of a linear association.

**Evidence:**
- [Original Pearson correlation and scatter plot](screenshots/ex1-pearson-original.png)
- [Modified Pearson correlation and scatter plot](screenshots/ex1-pearson-modified.png)

## 3. Exercise 2 — Simple linear regression

**Change:** I changed the final observed `y` value from `86` to `110`, keeping the `x` values unchanged. I calculated the correlation, fitted slope and prediction when `x = 10` using both versions of the dataset.

```python
# Original final value in y: 86
# Modified final value in y: 110
# The remaining values and x array were unchanged.
```

| Measure                 | Original | Modified |
| ----------------------- | -------: | -------: |
| Pearson correlation     |  -0.7586 |  -0.7316 |
| Regression slope        |  -1.7513 |  -1.9367 |
| Predicted y when x = 10 |  85.5931 |  86.9971 |

**Observation:** Both datasets showed a negative linear relationship. After I changed one observation, the correlation became slightly less negative, the slope became steeper in the negative direction and the predicted value at `x = 10` increased to approximately 87.00. This demonstrated that a fitted regression line and its predictions can be sensitive to individual observations.

**Evidence:**
- [Original regression graph](screenshots/ex2-linear-original.png)
- [Original prediction at x = 10](screenshots/ex2-prediction-original.png)
- [Modified regression graph](screenshots/ex2-linear-modified.png)
- [Modified prediction at x = 10](screenshots/ex2-prediction-modified.png)

## 4. Exercise 3 — Multiple linear regression

**Dataset:** `cars.csv`, containing 36 records and five columns. The fitted model used `Weight` and `Volume` to predict `CO2`.

**Change:** I kept the dataset, trained model and engine volume fixed, but changed the **prediction input** for vehicle weight from `2300` to `3300`. Unlike Exercise 2, this experiment changed the input supplied to an already fitted model rather than changing its training observations.

| Input or result             | Original prediction | Modified prediction |
| --------------------------- | ------------------: | ------------------: |
| Weight                      |                2300 |                3300 |
| Volume                      |                1300 |                1300 |
| Predicted CO2               |            107.2087 |            114.7597 |
| Difference in predicted CO2 |                   — |             +7.5509 |

**Observation:** With engine volume held at 1300, the model predicted a higher CO2 value for the heavier vehicle. The prediction increased by about 7.55 units for a 1000-unit increase in weight. This is a relationship represented by the fitted model; it does not independently prove that changing weight causes a change in emissions. I also corrected a scikit-learn feature-name warning by passing a DataFrame with the original `Weight` and `Volume` column names at prediction time.

**Evidence:**
- [Original multiple-regression prediction](screenshots/ex3-multiple-regression-original.png)
- [Modified multiple-regression prediction](screenshots/ex3-multiple-regression-modified.png)

## 5. Exercise 4 — Polynomial regression

**Change:** I changed one observed `y` value from `55` to `85`, keeping the `x` values, polynomial degree (`3`) and prediction input (`x = 17`) unchanged. I updated the data consistently in the curve, R² and prediction cells.

| Measure                  | Original | Modified |
| ------------------------ | -------: | -------: |
| Changed y observation    |       55 |       85 |
| Polynomial degree        |        3 |        3 |
| R² on the fitted dataset |   0.9432 |   0.8109 |
| Predicted y at x = 17    |  88.8733 |  87.4368 |

**Observation:** The R² value decreased when one observation was moved away from the original pattern. The fitted curve also changed, and the prediction at `x = 17` dropped by about 1.44, although that observation was not directly edited. This showed me how a single data point can affect the shape of a polynomial fit and predictions elsewhere. These R² values were calculated on the **training data**, so they do not establish performance on unseen data.

**Evidence:**
- [Original polynomial curve](screenshots/ex4-polynomial-original.png)
- [Original R² score](screenshots/ex4-r2-original.png)
- [Original prediction at x = 17](screenshots/ex4-prediction-original.png)
- [Modified polynomial curve](screenshots/ex4-polynomial-modified.png)
- [Modified R² score](screenshots/ex4-r2-modified.png)
- [Modified prediction at x = 17](screenshots/ex4-prediction-modified.png)

## 6. Overall learning and limitations

These four experiments showed me that changing data or prediction inputs can change a reported relationship, fitted model or predicted outcome. In particular, correlation does not establish causation, regression predictions are affected by the available observations, and a good fit to the data used for training is not proof that a model will generalise well.

The exercises also reminded me why it matters to explain exactly what changed. In Exercises 1, 2 and 4, I modified the observations or generated data; in Exercise 3, I changed only the input passed into the trained model. That distinction affects what conclusions I can reasonably draw.

**Learning outcomes addressed:**
- **LO2:** Understand the applicability and challenges associated with different datasets for machine learning algorithms.
- **LO1:** Articulate legal, social, ethical and professional issues — relevant here to responsible reporting of uncertainty, limits and the risk of mistaking correlation for causation.

**Supporting material:** Four executed Unit 3 notebooks, the `cars.csv` dataset for Exercise 3 and the screenshots linked above. These should be retained in the same evidence folder.
