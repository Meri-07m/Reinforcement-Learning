# 🧩 Reinforcement Learning in Maze Environments

This directory is part of the **[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by **[Meri-07m](https://github.com/Meri-07m)**.  
It focuses on implementing and experimenting with **reinforcement learning algorithms in maze environments**, providing a platform for testing, analyzing, and visualizing agent learning behavior in structured, discrete spaces.

Maze environments are classic benchmarks in RL research and educational exercises, making them ideal for understanding fundamental RL principles.

---

## 🌍 Project Overview

In reinforcement learning (RL), an **agent** learns to make decisions by interacting with an **environment**. A maze environment provides:

- A **discrete state space** corresponding to each cell in the maze.
- **Actions** like moving up, down, left, or right.
- **Rewards** for reaching the goal or penalties for invalid moves.
- **Terminal states** representing success (goal) or failure.

This module allows users to:

- Test different RL algorithms in a controlled environment.
- Analyze **learning efficiency** and **convergence** of agents.
- Compare performance across different **maze sizes**, **complexities**, and **reward structures**.
- Visualize agent trajectories, heatmaps, and policy evolution.

The folder also serves as a **teaching resource**, helping new RL practitioners understand concepts such as exploration vs. exploitation, value iteration, policy evaluation, and temporal difference learning.

---

---

## 🧠 Theoretical Background

Maze environments are **gridworld-style environments**, which are widely used to teach and benchmark RL algorithms. Key concepts include:

### 🔹 State Space
- Each cell in the maze is a **unique state**.
- Special states include **start**, **goal**, and possibly **traps or obstacles**.

### 🔹 Action Space
- Discrete actions: `up`, `down`, `left`, `right`.
- Invalid actions may either:
  - Keep the agent in the same cell.
  - Penalize with a negative reward.

### 🔹 Rewards
- **Goal state**: high positive reward (e.g., +1).
- **Step penalty**: optional small negative reward to encourage shorter paths.
- **Obstacle or trap**: negative reward to discourage unsafe paths.

### 🔹 RL Algorithms Implemented
| Algorithm | Type | Description |
|-----------|------|-------------|
| **Q-Learning** | Off-policy | Learns optimal action-value function using the max future reward. |
| **SARSA** | On-policy | Updates value based on the action actually taken in the next state. |
| **Deep Q-Network (DQN)** | Off-policy with function approximation | Uses neural networks to approximate Q-values in larger or continuous mazes. |

### 🔹 Learning Dynamics
- Agents balance **exploration** (trying new moves) and **exploitation** (following the best-known path).
- Hyperparameters like **learning rate (α)**, **discount factor (γ)**, and **exploration rate (ε)** significantly influence convergence speed and policy quality.
- The maze allows observation of **policy evolution**, learning curves, and trajectory heatmaps.



