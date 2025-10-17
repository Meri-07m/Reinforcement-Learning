# 🧠 Reinforcement Learning Repository

Welcome to the **Reinforcement-Learning** repository by **Meri-07m**. This repository is a comprehensive collection of reinforcement learning (RL) algorithms, experiments, and educational projects. It provides a wide range of implementations, from basic tabular methods to advanced function approximation techniques, designed to help learners, researchers, and enthusiasts explore the field of RL in depth.

This repository is structured to support both **learning and research**, offering clear examples, modular codebases, and visualizations to analyze agent behavior.

---

## 🌍 Repository Overview

The repository contains several **submodules**, each dedicated to a specific RL problem, algorithm, or technique. Below is a detailed description of each:

### 1. `random-walk-ntd`
Focuses on **Random Walk problems using Natural Temporal Difference (NTD) learning**.  
- Demonstrates how agents can learn optimal policies in stochastic environments.  
- Explores convergence behavior of TD methods with different parameters.  
- Includes trajectory sampling and state-value visualization.

### 2. `random-walk-fa`
Implements **Function Approximation (FA)** for random walk environments.  
- Allows learning in larger or continuous state spaces.  
- Uses linear function approximation to estimate state values.  
- Helps study generalization in RL and efficiency improvements over tabular methods.

### 3. `trajectory-sampling`
Experiments with **trajectory sampling methods**.  
- Samples full or partial trajectories to estimate returns.  
- Compares different sampling strategies and their impact on learning efficiency.  
- Includes visualizations for trajectory lengths, returns, and state visitation frequencies.

### 4. `updates-comparison`
Analyzes **different update rules in RL**, such as:  
- Q-Learning  
- SARSA  
- Expected SARSA  
- Compares convergence rates, stability, and policy performance in benchmark tasks.  
- Useful for understanding trade-offs between on-policy and off-policy learning.

### 5. `mazes`
Provides **maze environments** for RL experiments.  
- Includes gridworld mazes with walls, start, and goal positions.  
- Implements Q-Learning, SARSA, and optionally DQN agents.  
- Allows analysis of state visitation heatmaps, trajectory paths, and policy evolution.  
- Supports custom maze sizes and obstacle configurations.

### 6. `coarse-coding`
Implements **coarse coding techniques** for function approximation.  
- Tile coding: multiple overlapping grids to represent states.  
- Radial Basis Functions (RBFs): smooth representation of continuous states.  
- Integrates with Q-Learning and SARSA to study generalized learning.  
- Useful in large or continuous environments where tabular methods fail.

### 7. `gambler-problem`
Models the **Gambler's Problem**, a classical dynamic programming example.  
- Implements policy evaluation and improvement.  
- Demonstrates optimal policy derivation using value iteration.  
- Provides insights into risk-sensitive decision-making.

### 8. `gridworld-dp`
Explores **Dynamic Programming (DP) in gridworlds**.  
- Implements value iteration and policy iteration.  
- Serves as an educational tool to understand foundational RL algorithms.  
- Includes visualization of value functions and optimal policies.

### 9. `gridworld-mdp`
Focuses on **Markov Decision Processes (MDPs)** in gridworlds.  
- Supports stochastic transitions, reward shaping, and policy evaluation.  
- Demonstrates the impact of discount factors and different policies.  
- Provides a foundation for understanding the mathematical framework of RL.

### 10. `infinite-variance`
Investigates RL scenarios with **infinite variance rewards**.  
- Challenges standard TD and Monte Carlo methods.  
- Explores alternative learning strategies for robust performance.  
- Useful for research on rare-event learning or heavy-tailed distributions.

### 11. `ten-armed-testbed`
Implements the **Ten-Armed Testbed** for multi-armed bandit problems.  
- Evaluates exploration strategies such as epsilon-greedy and softmax.  
- Demonstrates learning dynamics in stationary and non-stationary settings.  
- Includes statistical analysis of reward distributions and cumulative returns.

### 12. `tic-tac-toe`
Provides RL implementations for the **Tic-Tac-Toe game**.  
- Uses Q-Learning and SARSA to learn optimal strategies.  
- Demonstrates policy convergence and winning strategies.  
- Serves as an example of RL in discrete action spaces.

### 13. `windy-gridworld`
Implements the **Windy Gridworld environment**.  
- Introduces stochastic transitions to challenge exploration-exploitation trade-offs.  
- Includes comparisons between different RL agents.  
- Visualizes trajectories and policy adaptation under uncertainty.

---

## 📚 Reinforcement Learning Concepts Covered

This repository covers a wide range of RL concepts, including:

- **Markov Decision Processes (MDPs)**  
- **Dynamic Programming (DP)**  
- **Temporal Difference (TD) Learning**  
- **Monte Carlo Methods**  
- **Function Approximation**  
- **Eligibility Traces**  
- **Policy Gradient and Actor-Critic (in future extensions)**  
- **Exploration vs Exploitation strategies**  

Each submodule provides code, experiments, and visualizations to help understand these concepts in depth.



