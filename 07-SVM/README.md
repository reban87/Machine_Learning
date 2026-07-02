# Support Vector Machines (SVM)

## What is SVM?

Support Vector Machine (SVM) is a **supervised machine learning algorithm** used for **classification and regression**, but it is mainly used for classification tasks.

SVM tries to find the **best separating hyperplane** that divides different classes with the **maximum margin**.

---

# Intuition

SVM finds a boundary that separates classes with the **largest possible gap (margin)**.

```text
Class +1        |        Class -1
○ ○ ○ ○         |         × × × ×
○ ○ ○ ○         |         × × × ×
                |
         Optimal Hyperplane
                |
```

The goal is not just to separate classes, but to separate them **as far apart as possible**.

---

# Key Idea

SVM chooses the hyperplane that:

- Maximizes margin between classes
- Minimizes classification error
- Uses only important points (support vectors)

---

# Hyperplane

A hyperplane is a decision boundary:

- 2D → line
- 3D → plane
- Higher dimensions → hyperplane

Mathematically:

$$
w \cdot x + b = 0
$$

Where:
- \( w \) = weight vector
- \( x \) = input vector
- \( b \) = bias

---

# Margin

Margin is the distance between the hyperplane and nearest data points.

SVM maximizes:

$$
Margin = \frac{2}{||w||}
$$

---

# Support Vectors

Support vectors are the **data points closest to the hyperplane**.

They are critical because:
- They define the margin
- Removing them changes the boundary
- Other points do not affect the model much

---

# SVM Diagram

<img width="716" height="561" alt="image" src="https://github.com/user-attachments/assets/d615bf9a-866f-4ba2-887c-1f5a8912d491" />


---

# Types of SVM

## 1. Linear SVM

Used when data is **linearly separable**.

```text
○ ○ ○ ○ | × × × ×
○ ○ ○ ○ | × × × ×
```

---

## 2. Non-Linear SVM

Used when data is not linearly separable.

Uses **Kernel Trick**.

---

# Kernel Trick

Transforms data into higher dimensions to make it separable.

Common kernels:

| Kernel | Use |
|--------|-----|
| Linear | Linearly separable data |
| Polynomial | Curved boundaries |
| RBF (Gaussian) | Most commonly used |
| Sigmoid | Neural-network-like behavior |

---

# Decision Function

SVM predicts using:

$$
f(x) = w \cdot x + b
$$

Decision rule:

```text
If f(x) ≥ 0 → Class +1
Else → Class -1
```

---

# Soft Margin SVM

Real-world data is not perfectly separable.

So SVM allows some errors using **C parameter**.

- High C → fewer errors, less margin
- Low C → more margin, more tolerance

---

# Hard Margin vs Soft Margin

| Hard Margin | Soft Margin |
|-------------|------------|
| No errors allowed | Allows misclassification |
| Works only for perfect separation | Works for real-world data |
| Sensitive to noise | Robust to noise |

---

# Example

```text
Training Data:

○ ○ ○ ○ ○
○ ○ ○ ○ ○

× × × × ×
× × × × ×
```

SVM finds the best line:

```text
○ ○ ○ | × × ×
○ ○ ○ | × × ×
```

---

# Advantages

- Works well in high-dimensional spaces
- Effective for small datasets
- Memory efficient (uses support vectors only)
- Strong theoretical foundation
- Works well with clear margins

---

# Disadvantages

- Not suitable for very large datasets
- Slow training on big data
- Sensitive to kernel choice
- Hard to interpret
- Requires feature scaling

---

# Applications

- Image classification
- Text classification
- Spam detection
- Bioinformatics
- Face detection
- Handwriting recognition

---

# SVM vs Logistic Regression

| SVM | Logistic Regression |
|-----|---------------------|
| Maximizes margin | Models probability |
| Works well in high dimensions | Simple probabilistic model |
| Uses support vectors | Uses all data points |
| Hard boundary | Smooth boundary |

---

# Workflow

```text
Training Data
      │
      ▼
Choose Kernel
      │
      ▼
Transform Feature Space
      │
      ▼
Find Optimal Hyperplane
      │
      ▼
Maximize Margin
      │
      ▼
Final SVM Model
```

---

# Summary

- SVM is a supervised classification algorithm.
- Finds the optimal hyperplane with maximum margin.
- Uses support vectors to define decision boundary.
- Kernel trick allows non-linear classification.
- Very powerful for high-dimensional data.
