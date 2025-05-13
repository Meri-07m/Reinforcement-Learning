# 🌬️ Windy Gridworld with Reinforcement Learning

This project demonstrates the application of **Reinforcement Learning (RL)** algorithms to solve the **Windy Gridworld** problem, a classic example used to illustrate the challenges of learning optimal policies in environments with stochastic elements.

## 📌 Overview

In the Windy Gridworld environment, an agent navigates a 7x10 grid from a designated start state to a goal state. The challenge arises from the presence of "windy" columns (4 to 9) that push the agent upward, introducing stochasticity into the environment. The agent receives a reward of -1 for each step taken, and the episode ends when the agent reaches the goal state.

## 🧠 Algorithms Implemented

The project includes implementations of the following RL algorithms:

- **Q-Learning**: An off-policy algorithm that learns the value of the optimal policy using the Bellman equation.
- **SARSA (State-Action-Reward-State-Action)**: An on-policy algorithm that updates the action-value function based on the action actually taken.
