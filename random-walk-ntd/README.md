# 🚶 Random Walk — NTD (n-step Temporal Difference)

This folder is part of the **[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by **[Meri-07m](https://github.com/Meri-07m)**.  
It focuses on the **Random Walk environment** and the implementation of **n-step Temporal Difference (NTD) learning**, a fundamental algorithm in reinforcement learning for predicting state values efficiently over time.

---

## 🌍 Overview

The **Random Walk environment** is a simple but illustrative Markov process commonly used to demonstrate and test reinforcement learning algorithms. An agent starts in a central state and moves either left or right at each time step until reaching a terminal state. Rewards are typically assigned at the terminal states, and the goal is to **predict the value of each non-terminal state**.

This module implements **n-step Temporal Difference learning**, an extension of the standard TD(0) method, which allows the agent to update value estimates based on multiple future steps rather than just the next step. This approach provides a **trade-off between bias and variance** in value estimation, bridging the gap between **Monte Carlo methods** and **one-step TD learning**.

---

## ⚡ Key Features

- 🏃 **Random Walk Environment**  
  A simple chain of states representing positions along a walk.  
  - Agent starts in the middle state.  
  - Moves left or right with equal probability.  
  - Terminal states provide reward feedback.

- 🔁 **n-step Temporal Difference Learning**  
  - Generalization of TD(0) to n steps ahead.  
  - Updates value estimates using **n-step returns**.  
  - Can be tuned via the `n` parameter to balance **bias vs. variance**.  
  - Useful for both policy evaluation and prediction tasks.

- 📊 **Performance Analysis & Visualization**  
  - Compare convergence of different n-step values.  
  - Plot value estimates over episodes.  
  - Analyze speed of learning and stability across multiple runs.

- 🎯 **Educational Demonstration**  
  - Ideal for understanding fundamental RL concepts:  
    - TD learning  
    - n-step returns  
    - Prediction vs. control  
    - Bias-variance trade-offs

---

## 🧩 How It Works

1. **Environment Setup**  
   The Random Walk environment is initialized with a fixed number of states and terminal conditions. The agent always starts from the central state.

2. **Agent Interaction**  
   The agent selects actions (move left or right) randomly, simulating the stochastic nature of the environment.

3. **Value Updates**  
   Using the n-step TD algorithm:  
   - Keep a rolling buffer of recent rewards and states.  
   - Calculate the **n-step return** for each state.  
   - Update the value function using the TD update rule.  

4. **Evaluation**  
   - Track the difference between estimated and true state values.  
   - Visualize convergence and compare different `n` values.

---

## 📦 Files & Structure

- `random_walk_ntd.py` — Main implementation of the n-step TD algorithm in the Random Walk environment.  
- `plot_results.py` — Scripts for visualizing the learning curves and performance comparisons.  
- `README.md` — Documentation and explanation of the folder contents.  

---

## 💡 Why It Matters

The Random Walk example with n-step TD is a **classic benchmark** in reinforcement learning:

- Provides a **controlled, easy-to-understand environment** to study learning dynamics.  
- Demonstrates **temporal credit assignment**, a core concept in RL.  
- Bridges simple TD learning and Monte Carlo methods, illustrating **the effect of the n-step parameter on learning efficiency**.  

It is a perfect starting point for students, researchers, or hobbyists to explore **predictive RL algorithms** before moving on to more complex domains like Gridworlds, Atari games, or continuous control tasks.

---

## 🚀 Getting Started
