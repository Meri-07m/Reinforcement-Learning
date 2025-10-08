# 🃏 Gambler’s Problem in Reinforcement Learning

This project implements the **Gambler’s Problem**, a classic example from Sutton and Barto's *Reinforcement Learning: An Introduction*, using **Dynamic Programming** methods such as **Value Iteration**.

## 📌 Problem Overview

In this setup:

- The gambler bets on the flip of a biased coin.
- If heads, the stake is added to their capital.
- If tails, the stake is lost.
- The goal is to reach a target capital (e.g., $100) starting from a smaller amount (e.g., $1).
- The agent must learn an optimal policy to maximize the probability of reaching the goal.

## 🧠 Key Learning Topics

- Markov Decision Process (MDP) formulation
- Bellman optimality equation
- Value Iteration for policy computation
- Visualization of optimal strategies

## 🧮 Algorithms Used

- **Value Iteration**: Iterative dynamic programming algorithm to compute the optimal state-value function.
- **Policy Extraction**: Derives the optimal action from the value function.
