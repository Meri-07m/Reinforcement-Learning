# 🚶 Random Walk — Function Approximation (FA)

This folder is part of the **[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by **[Meri-07m](https://github.com/Meri-07m)**.  
It focuses on the **Random Walk environment** combined with **Function Approximation (FA)** techniques in reinforcement learning, enabling the prediction of state values when explicit tabular representations are impractical.

---

## 🌍 Overview

The **Random Walk environment** is a simple, linear chain of states used to illustrate and evaluate reinforcement learning algorithms. An agent begins in the central state and moves either left or right at each time step until it reaches a terminal state. Rewards are usually given only at terminal states, making the task one of **state value prediction**.

In real-world scenarios, environments can have **large or continuous state spaces**, making tabular methods infeasible. **Function approximation** addresses this by representing the value function as a parameterized function (e.g., linear combination of features, neural networks), allowing **generalization across states**.

This module implements **Linear Function Approximation** for the Random Walk environment, demonstrating how an agent can learn **approximate state values** effectively.

---

## ⚡ Key Features

- 🏃 **Random Walk Environment**  
  - Linear chain of states.  
  - Central start state with stochastic movement left or right.  
  - Terminal states provide reward feedback.  

- 🔧 **Linear Function Approximation (FA)**  
  - Represents the value function \(V(s)\) as a **linear combination of features**.  
  - Parameters are updated using **gradient-based TD learning**.  
  - Allows generalization to unseen states.  

- 📊 **Performance Analysis & Visualization**  
  - Compare learning with different **feature representations**.  
  - Track parameter convergence and prediction accuracy.  
  - Visualize approximation error over episodes.

- 🎯 **Educational Demonstration**  
  - Illustrates key concepts:  
    - Gradient-descent TD learning  
    - Feature-based representation  
    - Trade-off between bias and generalization  

---

## 🧩 How It Works

1. **Environment Setup**  
   The Random Walk environment initializes a linear chain of states with terminal boundaries. The agent starts in the central state.

2. **Feature Representation**  
   Each state is represented as a **feature vector** (e.g., binary, one-hot encoding, or overlapping features). The value function is approximated as:

   \[
   \hat{V}(s) = \mathbf{w}^\top \mathbf{x}(s)
   \]

   where \(\mathbf{w}\) are the learnable parameters, and \(\mathbf{x}(s)\) is the feature vector of state \(s\).

3. **Gradient TD Updates**  
   Using **temporal difference errors**, parameters are updated via:

   \[
   \mathbf{w} \leftarrow \mathbf{w} + \alpha \delta \mathbf{x}(s)
   \]

   where \(\delta = R + \gamma \hat{V}(s') - \hat{V}(s)\).

4. **Evaluation**  
   - Measure **mean squared error** between predicted and true values.  
   - Compare different feature designs and learning rates.  
   - Visualize learning progress and approximation accuracy.

---

## 📦 Files & Structure

- `random_walk_fa.py` — Main implementation of linear function approximation in the Random Walk environment.  
- `plot_results.py` — Scripts for visualizing value approximation and learning curves.  
- `README.md` — Documentation explaining the folder contents.  

---

## 💡 Why It Matters

Function approximation is a **cornerstone of modern RL**, essential for handling **large-scale or continuous state spaces**:

- Enables **generalization** beyond tabular methods.  
- Demonstrates **gradient-based learning** in RL.  
- Bridges **classical TD learning** with more advanced methods like **deep RL**.  

The Random Walk FA example provides a **controlled and visualizable setting** to understand function approximation mechanics before tackling complex environments.

---//github.com/Meri-07m/Reinforcement-Learning.git
cd Reinforcement-Learning/random-walk-fa
