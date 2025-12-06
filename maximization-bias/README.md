# 🎯 Maximization Bias — Reinforcement Learning

This folder is part of the **[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by **[Meri-07m](https://github.com/Meri-07m)**.  
It explores **maximization bias**, one of the most fundamental issues in value-based reinforcement learning, and demonstrates how **Double Q-Learning** provides a clean and powerful correction.

The code in this folder provides a complete experimental environment, detailed implementations, and a suite of visualizations illustrating how maximization bias affects learning dynamics.

---

# 🌍 What Is Maximization Bias?

In many RL methods, the agent estimates value functions using the expression:

\[
\max_{a} Q(s, a)
\]

However, early in training the Q-values are often *noisy* due to:

- random initialization  
- stochastic transitions  
- stochastic rewards  
- limited experience  

Taking the **maximum** over noisy estimates tends to select an **overestimated** action.  
This creates **maximization bias**, causing the agent to:

- overestimate future returns  
- learn unstable policies  
- converge more slowly  
- behave suboptimally  

---

# 📉 Why Does Maximization Bias Occur?

Consider a simple example:  
You have two actions, each with true expected value:

- Action A = 5  
- Action B = 5  

Due to noise, you observe:

| Trial | A | B | max |
|------|---|---|------|
| 1 | 6 | 3 | 6 |
| 2 | 3 | 7 | 7 |
| 3 | 5 | 4 | 5 |

Even though **both actions truly have value 5**, the `max` almost always overshoots it.


This leads standard Q-Learning to systematically **overestimate** values.

---

# 🚨 Why It Matters in RL

Maximization bias impacts:

### ✔ Learning speed  
Overestimated values create unstable updates.

### ✔ Action selection  
The agent may repeatedly select actions that *look* good due to noise.

### ✔ Exploration  
Biased optimism can hinder proper exploration.

### ✔ Function approximation  
Neural-network-based Q-learning (like DQN) is highly sensitive to overestimation.

### ✔ Real-world RL  
In robots, resource management, and control tasks, overestimation can cause unsafe or costly behavior.

---

# 🟦 Standard Q-Learning (Biased)

Standard Q-Learning uses the update:

\[
Q(s,a) \leftarrow Q(s,a) + \alpha\left[r + \gamma\max_{a'}Q(s',a') - Q(s,a)\right]
\]

The same Q-values are used to:

1. **select** the maximizing action  
2. **evaluate** the chosen action  

This coupling is the root cause of maximization bias.

---

# 🟩 Double Q-Learning (Bias-Reduced)

Double Q-Learning uses two independent estimators:

- \(Q_1\)
- \(Q_2\)

**One selects**, the other **evaluates**:

\[
Q_1(s,a) \leftarrow Q_1(s,a) + \alpha \left[r + \gamma Q_2(s', \arg\max_{a'} Q_1(s',a')) - Q_1(s,a) \right]
\]

The two Q-functions alternate roles.

### Why this works

- Selecting with \(Q_1\) but evaluating with \(Q_2\) breaks the correlation.
- Errors do not reinforce each other.
- Estimates stay centered around the correct value.


Shows how severely standard Q-Learning overshoots, especially early.

### **2. Convergence Stability**

- Q-Learning often oscillates due to inflated targets.
- Double Q-Learning converges smoothly.

### **3. Action-Selection Behavior**

Experiments measure:

- frequency of optimal vs suboptimal actions  
- number of times noisy actions are incorrectly preferred  

### **4. Noise Sensitivity Study**

Using adjustable environment randomness:

| Noise Level | Q-Learning | Double Q-Learning |
|-------------|------------|-------------------|
| Low | slight bias | near perfect |
| Medium | large bias | small bias |
| High | unstable | stable |

---

# 🧠 Theoretical Deep Dive

## 📌 The key identity behind maximization bias

For any random variables \(X_1, ..., X_n\):

\[
\mathbb{E}[\max_i X_i] \geq \max_i \mathbb{E}[X_i]
\]

This inequality explains why maximization over noisy samples **always leads to overestimation**.

## 📌 Why Double Q works mathematically

If:

- \(Q_1\) selects the best action
- \(Q_2\) evaluates it

Then their noise is **independent**.  
The expectation becomes:

\[
\mathbb{E}[Q_2(s', \arg\max Q_1(s',a))] \approx \text{true value}
\]

Thus no systematic upward drift.

---

# 🧭 Practical Implications

### ✔ Use Double Q-Learning for:
- stochastic environments  
- high-noise reward problems  
- discrete control tasks  
- function approximation (NNs)  
- off-policy learning  

### ✔ Required for stable DQN variants:
- Double DQN  
- Dueling Double DQN  
- NoisyNets DQN  

### ✔ Avoid pure Q-Learning in:
- continuous action discretization  
- multi-step bootstrapping  
- early training with high exploration  
- environments with reward variance  





