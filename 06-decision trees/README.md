# Decision Trees (Machine Learning)

## What is a Decision Tree?

A **Decision Tree** is a supervised machine learning algorithm used for **classification and regression**.  
It works by splitting the dataset into smaller subsets based on feature values, forming a tree-like structure.

It is one of the most **interpretable ML models**.

---

# Intuition

A decision tree works like a flowchart:

```text
            [Feature A?]
               /     \
            Yes       No
           /            \
     [Feature B?]     Class 0
       /     \
   Class 1   Class 0
```

---

# Types of Decision Trees

| Type | Use |
|------|-----|
| Classification Tree | Predict categorical output |
| Regression Tree | Predict continuous values |

---

# How Decision Trees Work

The algorithm splits data based on **best feature selection criteria**.

At each node:
1. Choose the best feature
2. Split the dataset
3. Repeat recursively
4. Stop when pure or max depth reached

---

# Splitting Criteria

## 1. Gini Impurity
Gini impurity measures how often a randomly chosen element from the set would be incorrectly labeled if it were randomly classified. 
Measures how “pure” a node is.

Imagine you have a bag of balls with different colors.

If all balls are the same color, you can always guess the color correctly.
If the bag contains a mix of colors, you'll sometimes guess wrong.

Gini Impurity measures the probability of making a wrong prediction if you randomly assign a class according to the class distribution in that node.

The lower the Gini impurity, the purer the node.

$$
Gini = 1 - \sum p_i^2
$$

- 0 = perfectly pure
- Higher value = more mixed classes

---

## 2. Entropy (Information Gain)

Entropy measures disorder. Entropy measures the uncertainty or disorder in a dataset
Imagine a box containing balls.

Box A
10 Red
0 Blue

Before picking a ball, you already know it will be Red.

There is no uncertainty.

Entropy = 0

Box B
5 Red
5 Blue

Before picking a ball, you don't know whether it will be Red or Blue.

There is maximum uncertainty.

Entropy = 1 (for two classes)

$$
Entropy = -\sum p_i \log_2(p_i)
$$

Information Gain:
Information Gain (IG) measures the reduction in entropy after splitting:
$$
IG = Entropy(parent) - Entropy(children)
$$

The tree chooses the split with **maximum information gain**.
Imagine you're trying to guess the answer to a yes/no question.

Entropy measures how confused you are before asking a question.
Information Gain measures how much your confusion decreases after asking that question.

For example:

Before asking: "Is the person a student?" → You are very uncertain.
After asking: Most possibilities are eliminated.

The question gave you a high information gain because it greatly reduced your uncertainty.
---

# Example

Suppose dataset:

| Outlook | Play Tennis |
|--------|------------|
| Sunny | No |
| Overcast | Yes |
| Rain | Yes |

Tree learns rules like:

```text
IF Outlook = Overcast → Play = Yes
IF Outlook = Sunny → No
IF Outlook = Rain → Yes
```

---

# Decision Tree Structure

```text
            Root Node
               │
       ┌───────┴────────┐
   Internal Node     Internal Node
       │                   │
   Leaf Node           Leaf Node
 (Final Output)      (Final Output)
```

---

# Important Terms

| Term | Meaning |
|------|--------|
| Root Node | First split |
| Internal Node | Decision point |
| Leaf Node | Final output |
| Branch | Condition path |
| Splitting | Dividing dataset |

---

# Overfitting Problem

Decision trees can **overfit** easily if they grow too deep.

Example:

- Perfect training accuracy
- Poor test performance

---

# Pruning (Solution)

Pruning reduces overfitting.

## Types:

### 1. Pre-pruning
Stop tree early:
- Max depth
- Min samples split

### 2. Post-pruning
Remove branches after training

---

# Decision Boundary Example

<img width="716" height="561" alt="image" src="https://github.com/user-attachments/assets/07f9c78d-4e74-4eae-8f90-c987b554d690" />

---

# How Prediction Works

```text
Input Features
      │
      ▼
Start at Root Node
      │
      ▼
Check Condition
      │
      ▼
Move Left / Right
      │
      ▼
Reach Leaf Node
      │
      ▼
Return Prediction
```

---

# Advantages

- Easy to understand and interpret
- Works with both numerical and categorical data
- Requires little data preprocessing
- Handles non-linear relationships
- Fast predictions

---

# Disadvantages

- Prone to overfitting
- Sensitive to small data changes
- Can create biased trees
- Not very stable (high variance)

---

# Applications

- Loan approval systems
- Medical diagnosis
- Fraud detection
- Customer segmentation
- Risk analysis
- Business decision-making systems

---

# Decision Tree vs Logistic Regression

| Decision Tree | Logistic Regression |
|--------------|--------------------|
| Non-linear model | Linear model |
| Rule-based | Probability-based |
| Easy to interpret | Statistically strong |
| Can overfit | Less prone to overfitting |
| No scaling required | Needs scaling sometimes |

---

# Workflow

```text
Training Data
      │
      ▼
Select Best Feature (Gini / Entropy)
      │
      ▼
Split Dataset
      │
      ▼
Build Tree Recursively
      │
      ▼
Stop Condition Reached
      │
      ▼
Final Decision Tree Model
```

---

# Summary

- Decision Tree is a supervised learning algorithm.
- Works by recursively splitting data.
- Uses Gini impurity or entropy for splitting.
- Highly interpretable model.
- Can overfit without pruning.
- Used widely in classification and regression tasks.
