# Unit 5 — Jaccard Distance / Dissimilarity Calculations

**Module:** Machine Learning  
**Activity:** Clustering — Jaccard Distance  
**University:** University of Essex Online

## 1. Activity Objective

The purpose of this activity was to calculate the Jaccard dissimilarity between three individuals using their medical test results. The exercise helped me understand how binary attributes can be used to measure differences between records, which is relevant when studying clustering techniques in machine learning.

## 2. Original Dataset

The following data was provided in the Unit 5 learning activity.

| Name | Gender | Fever | Cough | Test-1 | Test-2 | Test-3 | Test-4 |
| ---- | ------ | ----- | ----- | ------ | ------ | ------ | ------ |
| Jack | M      | Y     | N     | P      | N      | N      | A      |
| Mary | F      | Y     | N     | P      | A      | P      | N      |
| Jim  | M      | Y     | P     | N      | N      | N      | A      |

Following the activity instructions, I converted the asymmetric attributes into binary values:

- **Y (Yes) and P (Positive) = 1**
- **N (No/Negative) and A (Absent) = 0**

Gender was excluded from the calculation because the activity identifies it as a symmetric variable.

## 3. Binary Conversion

| Name | Fever | Cough | Test-1 | Test-2 | Test-3 | Test-4 |
| ---- | ----- | ----- | ------ | ------ | ------ | ------ |
| Jack | 1     | 0     | 1      | 0      | 0      | 0      |
| Mary | 1     | 0     | 1      | 0      | 1      | 0      |
| Jim  | 1     | 1     | 0      | 0      | 0      | 0      |

## 4. Jaccard Distance Formula

The formula used for asymmetric binary data is:

**Jaccard Distance = (f01 + f10) / (f01 + f10 + f11)**

Where:

- **f11:** Both individuals have a value of 1.
- **f10:** First individual has 1 and second has 0.
- **f01:** First individual has 0 and second has 1.
- **f00:** Both individuals have 0 (excluded from the calculation).

## 5. Calculations

### Jack and Mary

The two individuals share positive values for Fever and Test-1. They differ on Test-3.

- f11 = 2
- f10 = 0
- f01 = 1

Jaccard Distance = (0 + 1) / (0 + 1 + 2)

**Result = 1/3 = 0.33**

### Jack and Jim

They share a positive Fever value but differ on Cough and Test-1.

- f11 = 1
- f10 = 1
- f01 = 1

Jaccard Distance = (1 + 1) / (1 + 1 + 1)

**Result = 2/3 = 0.67**

### Jim and Mary

They share a positive Fever value but differ on Cough, Test-1 and Test-3.

- f11 = 1
- f10 = 1
- f01 = 2

Jaccard Distance = (1 + 2) / (1 + 2 + 1)

**Result = 3/4 = 0.75**

## 6. Final Results

| Comparison    | Jaccard Distance |
| ------------- | ---------------- |
| Jack and Mary | 0.33             |
| Jack and Jim  | 0.67             |
| Jim and Mary  | 0.75             |

All three calculated values match the expected results provided in the university activity.

## 7. Interpretation

Jack and Mary have the lowest Jaccard Distance (0.33), which indicates that they are the most similar pair when considering the positive attributes.

Jim and Mary have the highest Jaccard Distance (0.75), making them the most dissimilar pair.

The exercise demonstrates that shared positive features contribute to similarity, while differences increase the Jaccard Distance. Shared zero values are excluded because the calculation focuses on the presence of asymmetric binary attributes.


