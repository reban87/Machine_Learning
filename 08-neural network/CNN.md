# 3.5 Convolutional Neural Networks (CNN)

## What is CNN?

A **Convolutional Neural Network (CNN)** is a type of deep learning model designed specifically for **image data processing**.

CNNs automatically learn:
- edges
- shapes
- textures
- complex objects

They are widely used in **computer vision** tasks.

---

# Why CNN instead of ANN?

Fully connected networks (MLPs):
- Too many parameters
- Ignore spatial structure of images

CNN solves this by:
- Using **local feature detection**
- Reducing parameters using **shared weights**

---

# CNN Architecture

```text
Input Image → Convolution → ReLU → Pooling → Flatten → Fully Connected → Output
```

---

# Key Components of CNN

## 1. Convolution Layer

Applies filters (kernels) to extract features.

### Operation:

$$
FeatureMap = Input * Filter
$$

Example filter detects edges:

```text
1  0 -1
1  0 -1
1  0 -1
```

---

## 2. Feature Maps

Output after applying filters.

- Detects patterns like edges and shapes
- Multiple filters → multiple feature maps

---

## 3. Activation Function (ReLU)

$$
f(x) = \max(0, x)
$$

Adds non-linearity.

---

## 4. Pooling Layer

Reduces spatial size while keeping important features.

### Types:
- Max Pooling
- Average Pooling

Example:

```text
Input:
1 3
2 4

Max Pool → 4
```

---

## 5. Flattening

Converts 2D feature maps into 1D vector.

---

## 6. Fully Connected Layer

Final classification layer (like MLP).

---

# CNN Workflow

```text
Image
  │
  ▼
Convolution Layer
  │
  ▼
ReLU Activation
  │
  ▼
Pooling Layer
  │
  ▼
Flatten
  │
  ▼
Fully Connected Layer
  │
  ▼
Output Prediction
```

---

# CNN Applications

- Image classification
- Face recognition
- Object detection
- Medical imaging
- Self-driving cars

---

# Advantages

- Automatically extracts features
- Reduces number of parameters
- Highly accurate for images
- Translation invariant

---

# Disadvantages

- Requires large datasets
- Computationally expensive
- Hard to interpret


---

# CNN Diagram (Add Image)

```markdown
![CNN Architecture](images/cnn_architecture.svg)
```

---

---

# 3.5 Recurrent Neural Networks (RNN)

## What is RNN?

A **Recurrent Neural Network (RNN)** is designed for **sequential data** such as:
- text
- speech
- time series

It has memory to remember previous inputs.

---

# Why RNN?

Unlike CNNs, RNNs handle:
- order of data
- time dependencies

Example:
- Sentence understanding depends on previous words

---

# RNN Structure

```text
x(t) → [ RNN Cell ] → y(t)
           ↑
        memory
```

---

# Working of RNN

At each time step:

$$
h_t = f(Wx_t + Uh_{t-1} + b)
$$

Where:
- \(h_t\) = hidden state
- \(x_t\) = input at time t
- \(h_{t-1}\) = previous memory

---

# Unrolled RNN

```text
x1 → x2 → x3 → x4
 |    |    |    |
h1 → h2 → h3 → h4
```

---

# Problems in RNN

## 1. Vanishing Gradient
- Cannot learn long-term dependencies

## 2. Exploding Gradient
- Very large updates during training

---

# Applications

- Language modeling
- Speech recognition
- Stock prediction
- Machine translation

---

---

# 3.6 Reinforcement Learning (RL)

## What is RL?

Reinforcement Learning is a learning method where an **agent learns by interacting with an environment**.

It learns through:
- trial and error
- rewards and penalties

---

# Key Components

## 1. Agent

The learner or decision maker.

Example:
- Robot
- Game AI

---

## 2. Environment

Everything the agent interacts with.

Example:
- Game world
- Real world

---

## 3. State (S)

Current situation of the agent.

Example:
- Position in a maze

---

## 4. Action (A)

Choices available to the agent.

Example:
- move left
- move right

---

## 5. Reward (R)

Feedback signal.

- Positive reward → good action
- Negative reward → bad action

---

## 6. Policy (π)

Strategy used by agent:

$$
\pi(a|s)
$$

Means: probability of taking action *a* in state *s*

---

# RL Loop

```text
Agent → Action → Environment → Reward → New State → Agent
```

---

# Goal of RL

Maximize total reward:

$$
\sum R_t
$$

---

# Applications

- Robotics
- Game AI (AlphaGo)
- Self-driving cars
- Recommendation systems

---

---

# 3.6 Q-Learning

## What is Q-Learning?

Q-Learning is a reinforcement learning algorithm that learns the **best action for each state**.

It uses a Q-table:

| State | Action | Q-value |
|------|--------|--------|

---

# Q-Value

Represents how good an action is:

$$
Q(s,a)
$$

---

# Update Rule

$$
Q(s,a) = Q(s,a) + \alpha [R + \gamma \max Q(s',a') - Q(s,a)]
$$

Where:
- α = learning rate
- γ = discount factor
- R = reward

---

# Q-Learning Process

```text
Initialize Q-table
      │
      ▼
Choose Action (exploration/exploitation)
      │
      ▼
Get Reward
      │
      ▼
Update Q-value
      │
      ▼
Repeat
```

---

# Exploration vs Exploitation

| Exploration | Exploitation |
|------------|-------------|
| Try new actions | Use best known action |
| Learn more | Use knowledge |

---

# Applications

- Game AI
- Robotics
- Navigation systems

---

---

# 3.7 Hybrid Expert Systems (Rule + ML)

## What are Hybrid Expert Systems?

These systems combine:
- **Rule-based systems (traditional AI)**
- **Machine Learning models**

They improve decision-making by combining:
- human knowledge
- data-driven learning

---

# Architecture

```text
Input Data
   │
   ├── Rule-Based System
   │
   ├── Machine Learning Model
   │
   ▼
Final Decision Engine
```

---

# Rule-Based System

Uses IF-THEN rules:

```text
IF temperature > 100 THEN alert = "High"
```

Pros:
- Easy to interpret
- Fast decisions

Cons:
- Not flexible
- Hard to scale

---

# Machine Learning System

Learns patterns from data.

Pros:
- Learns automatically
- Handles complex data

Cons:
- Less interpretable

---

# Hybrid Approach Benefits

- High accuracy
- Better interpretability
- Combines logic + learning
- Used in critical systems

---

# Applications

- Medical diagnosis systems
- Financial fraud detection
- Industrial automation
- Expert decision systems

---

---

# 3.7 Data-Driven Knowledge Bases

## What is a Data-Driven Knowledge Base?

A system where knowledge is **automatically learned from data** instead of manually written rules.

---

# Traditional vs Data-Driven

| Traditional KB | Data-Driven KB |
|---------------|---------------|
| Manually created rules | Learned from data |
| Static | Dynamic |
| Limited scalability | Highly scalable |

---

# Structure

```text
Raw Data → Processing → Knowledge Extraction → Knowledge Base → Reasoning System
```

---

# Techniques Used

- Machine Learning
- Deep Learning
- NLP (for text knowledge extraction)
- Clustering & classification

---

# Example

From medical records:

```text
Symptoms → Disease prediction rules
```

Instead of writing rules manually, the system learns:

```text
IF cough + fever → flu (probability 0.87)
```

---

# Advantages

- Continuously improves
- Scalable
- Works with large datasets
- More accurate over time

---

# Disadvantages

- Requires large data
- Hard to interpret
- Requires training infrastructure

---

# Applications

- AI assistants
- Recommendation systems
- Healthcare systems
- Enterprise knowledge systems

---

# Summary

- CNN → image processing
- RNN → sequential data
- RL → learning via rewards
- Q-Learning → value-based RL method
- Hybrid systems → rule + ML combination
- Data-driven KB → knowledge learned from data
