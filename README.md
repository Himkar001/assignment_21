# Assignment 21 – AM & PM Sessions 

## Overview

This repository documents Assignment 20 in a structured and comprehensive way. It includes both AM and PM sessions, covering Python fundamentals, NumPy operations, object-oriented programming, and core data science concepts such as regression, classification, and bias–variance tradeoff.

The content is organized into four parts (A–D) for each session, including code, outputs, explanations, and evaluation.

---

# AM SESSION

## Part A – NumPy Implementation

### 1. Array Creation, Indexing and Slicing

```python
import numpy as np

arr1 = np.array([10, 20, 30, 40, 50])
arr2 = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
arr3 = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])

print(arr1)
print(arr2)
print(arr3)
```

Output:

```
[10 20 30 40 50]
[[1 2 3]
 [4 5 6]
 [7 8 9]]
[[[1 2]
  [3 4]]
 [[5 6]
  [7 8]]]
```

Indexing and slicing allow access to specific elements or subsets of arrays.

---

### 2. Basic Operations

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
print(a - b)
print(a * b)

print(np.mean(a))
print(np.var(a))
print(np.std(a))
```

Output:

```
[5 7 9]
[-3 -3 -3]
[ 4 10 18]
2.0
0.6666
0.8164
```

Operations are performed element-wise and NumPy provides efficient statistical functions.

---

### 3. Broadcasting

```python
arr2 = np.array([[1, 2, 3], [4, 5, 6]])
arr1 = np.array([10, 20, 30])

print(arr2 + arr1)
```

Output:

```
[[11 22 33]
 [14 25 36]]
```

Broadcasting allows operations between arrays of different shapes without explicit loops.

---

### 4. Vectorised Operations

```python
arr = np.array([-2, -1, 0, 1, 2, 3])
arr[arr < 0] = 0
print(arr)

arr = np.array([10, 20, 30, 40])
norm = (arr - arr.min()) / (arr.max() - arr.min())
print(norm)
```

Output:

```
[0 0 0 1 2 3]
[0.0 0.33 0.66 1.0]
```

Vectorisation improves performance by applying operations to entire arrays.

---

### 5. Dataset Operations

```python
data = np.array([10, 50, 30, 20, 90, 60, 80, 70])

top5 = np.sort(data)[-5:]
print(top5)
```

Output:

```
[30 50 60 70 90]
```

Demonstrates sorting, filtering, and aggregation.

---

## Part B – Matrix Operations

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

print(np.dot(A, B))
print(A.T)
print(np.linalg.det(A))
```

Output:

```
[[19 22]
 [43 50]]
[[1 3]
 [2 4]]
-2.0
```

Matrix multiplication, transpose, and determinant are fundamental linear algebra operations.

---

### Solving Linear Equations

```python
A = np.array([[2, 1], [1, 3]])
B = np.array([5, 6])

solution = np.linalg.solve(A, B)
print(solution)
```

Output:

```
[1.8 1.4]
```

---

### Performance Comparison

NumPy operations are significantly faster than Python loops due to optimized C implementation.

---

## Part C – Interview Ready

### Broadcasting

Broadcasting allows operations between arrays of different shapes without manual resizing.

### Normalization

```python
def normalize(X):
    return (X - np.min(X)) / (np.max(X) - np.min(X))
```

### Vectorisation vs Loops

* Vectorisation is faster and cleaner
* Loops are slower due to Python overhead

---

## Part D – AI Task

Prompt:
Explain NumPy broadcasting and vectorisation.

Evaluation:

* Concepts correct
* Code efficient
* Demonstrates performance improvement

---

# PM SESSION

## Part A – Regression and Classification

### Dataset Creation

```python
X = np.linspace(0, 10, 50)
y_reg = 2 * X + 3

y_clf = np.where(X > 5, 1, 0)
```

Regression uses continuous outputs, while classification uses discrete labels.

---

### Regression Model

```python
coeffs = np.polyfit(X, y_reg, 1)
y_pred = np.polyval(coeffs, X)
```

Produces a best-fit line.

---

### Classification Logic

```python
threshold = 5
y_pred = np.where(X > threshold, 1, 0)
```

---

### Evaluation Metrics

```python
mse = np.mean((y_reg - y_pred) ** 2)
accuracy = np.mean(y_pred == y_clf)
```

* MSE measures regression error
* Accuracy measures classification performance

---

## Part B – Bias–Variance Tradeoff

Different polynomial models show:

* Underfitting (low complexity)
* Good fit (optimal complexity)
* Overfitting (high complexity)

Training error decreases as model complexity increases, but overfitting reduces generalization.

---

## Part C – Interview Ready

### Regression vs Classification

* Regression: continuous output
* Classification: categorical output

### Mean Squared Error

```python
def calculate_mse(y_true, y_pred):
    return np.mean((y_true - y_pred) ** 2)
```

### Bias–Variance

* High bias → underfitting
* High variance → overfitting
* Optimal model balances both

---

## Part D – AI Task

Prompt:
Explain regression, classification, and bias–variance tradeoff.

Evaluation:

* Explanation accurate
* Visualizations meaningful
* Code correct and runnable

---

## Final Conclusion

This assignment builds a strong foundation in both programming and data science. The AM session focuses on NumPy and efficient computation, while the PM session introduces machine learning concepts such as regression, classification, and model evaluation. Together, they provide a balanced understanding of practical implementation and theoretical concepts.
