# Linear Regression

## What is Linear Regression?

Linear Regression is a **supervised machine learning algorithm** used to predict a **continuous numerical value** by learning a linear relationship between one or more input features and a target variable.

### Examples

- Predicting house prices
- Forecasting sales
- Estimating temperatures
- Predicting exam scores

---

# Goal

The objective is to find the line (or hyperplane) that best fits the training data.

The model learns the following equation:

$$
\hat{y}=w_0+w_1x_1+w_2x_2+\cdots+w_nx_n
$$

Where

| Symbol | Meaning |
|---------|---------|
| $\hat{y}$ | Predicted value |
| $w_0$ | Bias (intercept) |
| $w_1,\ldots,w_n$ | Feature weights (coefficients) |
| $x_1,\ldots,x_n$ | Input features |

---

# Types of Linear Regression

## 1. Simple Linear Regression

Uses **one input feature**.

$$
\hat{y}=w_0+w_1x
$$

### Example

Predict salary from years of experience.

| Experience (Years) | Salary |
|-------------------:|-------:|
| 1 | \$40,000 |
| 3 | \$55,000 |
| 5 | \$72,000 |

---

## 2. Multiple Linear Regression

Uses **multiple input features**.

$$
\hat{y}=w_0+w_1x_1+w_2x_2+\cdots+w_nx_n
$$

Example features:

- House size
- Number of bedrooms
- Age of house
- Distance to city center

---

# How Linear Regression Learns

The algorithm adjusts its weights so that predictions are as close as possible to the actual values.

Prediction equation:

$$
\hat{y}=Xw+b
$$

---

# Residual (Prediction Error)

The prediction error is called the **residual**.

$$
e=y-\hat{y}
$$

Where

- $y$ = actual value
- $\hat{y}$ = predicted value

---

# Cost Function

Linear Regression minimizes the **Mean Squared Error (MSE)**.

$$
J(w)=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
$$

Properties:

- Always non-negative
- Penalizes larger errors more heavily
- Smooth and differentiable

---

# Training Methods

## 1. Normal Equation

Computes the optimal weights directly.

### Advantages

- Exact solution
- No learning rate required

### Disadvantages

- Computationally expensive for very large datasets

---

## 2. Gradient Descent

Updates weights iteratively.

Weight update rule:

$$
w:=w-\alpha\frac{\partial J}{\partial w}
$$

Where

- $\alpha$ = learning rate

Repeat until the cost function converges.

---

# Prediction Process

```text
Input Features
      │
      ▼
Multiply by Learned Weights
      │
      ▼
Add Bias
      │
      ▼
Predicted Value
```

---

# Evaluation Metrics

## Mean Absolute Error (MAE)

$$
MAE=\frac1n\sum|y-\hat{y}|
$$

- Easy to interpret
- Less sensitive to outliers

---

## Mean Squared Error (MSE)

$$
MSE=\frac1n\sum(y-\hat{y})^2
$$

- Penalizes large errors
- Most commonly used loss function

---

## Root Mean Squared Error (RMSE)

$$
RMSE=\sqrt{MSE}
$$

- Same units as the target variable
- Easier to interpret than MSE

---

## Coefficient of Determination ($R^2$)

$$
R^2=1-\frac{SS_{res}}{SS_{tot}}
$$

Interpretation

| $R^2$ | Meaning |
|--------|---------|
| 1 | Perfect prediction |
| 0 | No improvement over predicting the mean |
| < 0 | Worse than predicting the mean |

---

# Assumptions

Linear Regression assumes:

- Linear relationship between features and target
- Independent observations
- Constant variance (homoscedasticity)
- Normally distributed residuals
- Little or no multicollinearity
- No significant outliers

---

# Advantages

- Simple and easy to understand
- Fast training
- Highly interpretable
- Works well for linear relationships
- Low computational cost

---

# Disadvantages

- Only models linear relationships
- Sensitive to outliers
- Can underfit complex datasets
- Performance decreases with multicollinearity
- Assumptions may not always hold

---

# Example

Suppose the learned model is

$$
\hat{y}=2+3x
$$

If

$$
x=4
$$

Then

$$
\hat{y}=2+3(4)=14
$$

---

# Workflow

```text
Training Data
      │
      ▼
Feature Selection
      │
      ▼
Train Linear Regression Model
      │
      ▼
Learn Weights
      │
      ▼
Predict New Values
      │
      ▼
Evaluate Model Performance
```

---

# Applications

- House price prediction
- Sales forecasting
- Medical diagnosis support
- Energy consumption prediction
- Demand forecasting
- Risk estimation
- Economic forecasting

---

# Summary

- Supervised learning algorithm
- Predicts continuous values
- Learns a linear relationship between inputs and outputs
- Trained by minimizing Mean Squared Error (MSE)
- Outputs real-valued predictions
- Easy to interpret and implement
- Common baseline model for regression tasks
