# 🎰 Ten-Armed Testbed with Reinforcement Learning

This project implements the **Ten-Armed Testbed**, a classic problem in reinforcement learning used to evaluate the performance of various action-selection strategies, particularly focusing on the exploration-exploitation trade-off.

## 📌 Overview

The Ten-Armed Testbed consists of 10 slot machines (arms), each with a different, fixed probability distribution for generating rewards. The objective is to determine which arm to pull to maximize the cumulative reward over time. This problem is ideal for testing algorithms like ε-greedy, UCB, and others in a controlled, stochastic environment.

## 🧠 Algorithms Implemented

The project includes implementations of the following reinforcement learning algorithms:

- **ε-Greedy**: Selects the action with the highest estimated value most of the time, but with probability ε, selects a random action to encourage exploration.
- **Optimistic Initialization**: Initializes action-value estimates to high values to encourage exploration.
