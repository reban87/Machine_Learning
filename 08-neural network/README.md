# Neural Networks & Multi-Layer Perceptron (MLP)

## What is a Neural Network?

A **Neural Network** is a machine learning model inspired by the structure of the **human brain**. It consists of interconnected nodes called **neurons** that work together to learn patterns from data.

Neural networks are the foundation of **deep learning**.

---

# Why Neural Networks?

Traditional ML models struggle with complex, non-linear data.

Neural networks solve this by:
- Learning **non-linear relationships**
- Automatically extracting features
- Handling large and complex datasets

---

# Basic Structure of a Neural Network

A neural network has 3 main layers:

```text
Input Layer → Hidden Layers → Output Layer
```

### Diagram

```text
Input Layer        Hidden Layer         Output Layer
   x1  ○ ─────┐        ○ ─────┐             ○
   x2  ○ ─────┼──────▶ ○ ─────┼──────▶      ○
   x3  ○ ─────┘        ○ ─────┘             ○
```

---

# What is a Neuron?

A neuron performs a simple computation:

$$
z = w_1x_1 + w_2x_2 + \cdots + w_nx_n + b
$$

Then applies an activation function:

$$
a = f(z)
$$

Where:
- \( x \) = inputs
- \( w \) = weights
- \( b \) = bias
- \( f \) = activation function
- \( a \) = output

---

# Perceptron (Basic Neural Network)

A **Perceptron** is the simplest neural network.

It is used for **binary classification**.

### Equation:

$$
y = f(w \cdot x + b)
$$

If output ≥ threshold → Class 1  
Else → Class 0

---

# Multi-Layer Perceptron (MLP)

An **MLP** is a neural network with:

- Input layer
- One or more hidden layers
- Output layer

It can solve **non-linear problems**.

---

# MLP Architecture

```text
Input Layer → Hidden Layer 1 → Hidden Layer 2 → Output Layer
```

### Example:

```text
x1 ○ ─┐
x2 ○ ─┼──▶ ○ ○ ○ ──▶ ○ ○
x3 ○ ─┘
```

---

# Forward Propagation

Forward propagation is the process of moving input through the network.

Steps:

```text
Input → Weighted Sum → Activation → Next Layer → Output
```

Mathematically:

$$
z^{(l)} = W^{(l)} a^{(l-1)} + b^{(l)}
$$

$$
a^{(l)} = f(z^{(l)})
$$

---

# Activation Functions

Activation functions introduce **non-linearity**.

## 1. Sigmoid

$$
\sigma(x)=\frac{1}{1+e^{-x}}
$$

- Output: 0 to 1
- Used in binary classification

---

## 2. Tanh

$$
tanh(x)=\frac{e^x - e^{-x}}{e^x + e^{-x}}
$$

- Output: -1 to 1
- Zero-centered

---

## 3. ReLU (Most used)

$$
f(x)=\max(0,x)
$$

- Fast computation
- Reduces vanishing gradient problem

---

## 4. Softmax

Used in multi-class classification:

$$
\sigma(z_i)=\frac{e^{z_i}}{\sum e^{z_j}}
$$

---

# Backpropagation (Learning Process)

Backpropagation is how neural networks **learn**.

It updates weights using error correction.

---

## Steps:

```text
1. Forward pass (prediction)
2. Compute error (loss)
3. Backward pass (compute gradients)
4. Update weights
```

---

## Weight Update Rule:

$$
w := w - \alpha \frac{\partial L}{\partial w}
$$

Where:
- \( \alpha \) = learning rate
- \( L \) = loss function

---

# Loss Function

Common loss functions:

## Mean Squared Error (Regression)

$$
MSE = \frac{1}{n} \sum (y - \hat{y})^2
$$

## Cross Entropy (Classification)

$$
L = -\sum y \log(\hat{y})
$$

---

# Deep Neural Network

A deep network has **many hidden layers**:

```text
Input → Hidden → Hidden → Hidden → Output
```

More layers = better feature learning (for complex data)

---

# MLP vs Single Perceptron

| Feature | Perceptron | MLP |
|--------|------------|-----|
| Layers | 1 | Multiple |
| Problem type | Linear | Non-linear |
| Power | Limited | Powerful |
| Activation | Step function | Non-linear functions |

---

# Advantages of Neural Networks

- Can model complex relationships
- Works well with large datasets
- Automatically learns features
- Highly flexible
- Basis of deep learning systems

---

# Disadvantages

- Requires large data
- Computationally expensive
- Hard to interpret (black box)
- Requires tuning hyperparameters
- Training can be slow

---

# Applications

- Image recognition
- Speech recognition
- Machine translation
- Medical diagnosis
- Fraud detection
- Autonomous vehicles
- Chatbots (like LLMs)

---

# Workflow

```text
Input Data
    │
    ▼
Initialize Weights
    │
    ▼
Forward Propagation
    │
    ▼
Compute Loss
    │
    ▼
Backpropagation
    │
    ▼
Update Weights
    │
    ▼
Repeat Until Convergence
```

---

# Summary

- Neural networks are inspired by the human brain.
- A neuron computes weighted inputs + activation.
- MLP contains multiple hidden layers.
- Activation functions introduce non-linearity.
- Backpropagation is used for learning.
- Foundation of modern deep learning.
