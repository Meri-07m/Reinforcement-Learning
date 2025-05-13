# 🌀 Random Walk with Temporal Difference Learning

This project implements the **Random Walk** problem, a fundamental example in reinforcement learning that demonstrates how value prediction works using Temporal Difference (TD) methods.

## 📌 Overview

The Random Walk consists of a linear chain of states where an agent starts in the middle and moves left or right randomly. The episode ends when the agent reaches a terminal state (either far left or right). The agent learns value estimates of non-terminal states through interaction, with the goal of accurate prediction.

This setup is widely used to understand and visualize the dynamics of TD learning, especially TD(λ).

## 🧠 Algorithms Implemented

- **TD(0)** – Standard one-step temporal difference learning.
- **n-step TD** – Learns from the sum of rewards over `n` future steps.
- **TD(λ)** – Uses eligibility traces and λ-return for more generalized updates.
