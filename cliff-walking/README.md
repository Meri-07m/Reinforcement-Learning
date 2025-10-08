# 🧗 Cliff Walking — Reinforcement Learning

This project implements the **Cliff Walking** environment from Sutton & Barto's *Reinforcement Learning: An Introduction*, demonstrating **on-policy** and **off-policy** reinforcement learning algorithms.

## 📌 Problem Overview

In this gridworld environment:

- The agent starts at the bottom-left corner and aims to reach the bottom-right corner.
- The grid consists of a 4x12 matrix.
- Stepping on the cliff (cells between columns 1 and 10 in the last row) incurs a large negative reward (-100) and resets the agent to the start.
- Each step costs -1 reward.
- Reaching the goal (bottom-right corner) ends the episode with a positive reward.

## 🧠 Algorithms Implemented

- **SARSA (State-Action-Reward-State-Action)**: On-policy temporal difference control.
- **Q-learning**: Off-policy temporal difference control.
- **Monte Carlo Control**: Model-free method using complete episodes.
