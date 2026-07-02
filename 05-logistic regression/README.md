# Logistic Regression

## What is Logistic Regression?

Logistic Regression is a **supervised machine learning algorithm** used for **classification problems**.

Unlike Linear Regression, which predicts **continuous values**, Logistic Regression predicts the **probability** that an input belongs to a particular class.

It is mainly used for **binary classification**, where the output is one of two possible classes.

Examples:

- Email Spam Detection (Spam / Not Spam)
- Disease Prediction (Positive / Negative)
- Customer Churn (Leave / Stay)
- Loan Approval (Approved / Rejected)

---

# Classification vs Regression

| Regression | Classification |
|------------|---------------|
| Predicts continuous values | Predicts categories |
| House price | Spam detection |
| Temperature prediction | Cancer diagnosis |
| Sales prediction | Fraud detection |

---

# Why Not Use Linear Regression?

Suppose we use Linear Regression for classification.

The predicted values may become:

```text
-0.8
0.3
1.7
2.4
```

These are **not valid probabilities** because probabilities must lie between **0 and 1**.

Logistic Regression solves this by applying the **Sigmoid Function**, which converts any number into a value between **0 and 1**.

---

# Sigmoid Function

The sigmoid (logistic) function is

$$
P(y=1)=\frac{1}{1+e^{-z}}
$$

where

$$
z=w_0+w_1x_1+w_2x_2+\cdots+w_nx_n
$$

The sigmoid function always produces values between

$$
0 \le P \le 1
$$


# How Logistic Regression Works

```text
Input Features
      │
      ▼
Linear Equation
(z = wx + b)
      │
      ▼
Sigmoid Function
      │
      ▼
Probability
      │
      ▼
Apply Threshold
      │
      ▼
Final Class
```

---

# Decision Threshold

Usually,

- Probability ≥ 0.5 → Class 1
- Probability < 0.5 → Class 0

Example

| Probability | Prediction |
|-------------|-----------|
| 0.95 | 1 |
| 0.82 | 1 |
| 0.71 | 1 |
| 0.49 | 0 |
| 0.21 | 0 |

---

# Mathematical Model

First compute

$$
z=w_0+w_1x_1+w_2x_2+\cdots+w_nx_n
$$

Then compute the probability

$$
P(y=1)=\frac{1}{1+e^{-z}}
$$

Finally,

```text
If P ≥ 0.5
    Predict Class = 1

Else
    Predict Class = 0
```

---

# Example

Suppose

$$
z=2
$$

Then

$$
P(y=1)=\frac1{1+e^{-2}}
$$

Approximately,

$$
P(y=1)=0.88
$$

Since

```text
0.88 > 0.5
```

Prediction

```text
Class = 1
```

---

# Cost Function

Unlike Linear Regression, Logistic Regression **does not use Mean Squared Error**.

Instead, it uses **Log Loss (Binary Cross Entropy)**.

$$
J=-\frac1n
\sum
\left[
y\log(\hat y)
+
(1-y)\log(1-\hat y)
\right]
$$

Properties

- Penalizes incorrect predictions heavily
- Convex optimization problem
- Better suited for classification

---

# Training

The model learns the weights using **Gradient Descent**.

Weight update

$$
w:=w-\alpha\frac{\partial J}{\partial w}
$$

where

- α = learning rate

---

# Decision Boundary

The decision boundary separates different classes.

Example

```text
○ ○ ○ ○ ○ ○
○ ○ ○ ○ ○ ○

--------------------------

× × × × × ×
× × × × × ×
```

Everything above the line belongs to one class, while everything below belongs to the other.

---

# Performance Evaluation

Unlike regression, we evaluate classification models using:

## Accuracy

$$
Accuracy=
\frac{Correct\ Predictions}
{Total\ Predictions}
$$

---

## Precision

$$
Precision=
\frac{TP}
{TP+FP}
$$

Measures how many predicted positives are actually positive.

---

## Recall

$$
Recall=
\frac{TP}
{TP+FN}
$$

Measures how many actual positives are correctly identified.

---

## F1 Score

$$
F1=
2
\cdot
\frac{Precision\times Recall}
{Precision+Recall}
$$

Useful when classes are imbalanced.

---

# Confusion Matrix

| Actual / Predicted | Positive | Negative |
|-------------------|---------:|---------:|
| Positive | TP | FN |
| Negative | FP | TN |

Where

- TP = True Positive
- TN = True Negative
- FP = False Positive
- FN = False Negative

---

# Advantages

- Simple and easy to implement
- Fast training
- Outputs probabilities
- Works well for binary classification
- Easy to interpret

---

# Disadvantages

- Only learns linear decision boundaries
- Sensitive to outliers
- Cannot model complex relationships
- Requires feature scaling for best performance

---

# Applications

- Spam email detection
- Disease diagnosis
- Credit risk analysis
- Customer churn prediction
- Fraud detection
- Sentiment analysis

---

# Linear Regression vs Logistic Regression

| Linear Regression | Logistic Regression |
|------------------|--------------------|
| Regression | Classification |
| Predicts numbers | Predicts probabilities |
| Uses MSE | Uses Log Loss |
| Output is continuous | Output ranges from 0 to 1 |
| Best-fit line | Sigmoid curve |

---

# Workflow

```text
Training Data
      │
      ▼
Feature Selection
      │
      ▼
Linear Equation
      │
      ▼
Sigmoid Function
      │
      ▼
Probability
      │
      ▼
Threshold
      │
      ▼
Predicted Class
      │
      ▼
Evaluate Model
```

---

# Summary

- Logistic Regression is a supervised classification algorithm.
- It predicts probabilities instead of continuous values.
- Uses the Sigmoid Function to map values between 0 and 1.
- Uses Log Loss as the cost function.
- Trained using Gradient Descent.
- Commonly used for binary classification problems.
