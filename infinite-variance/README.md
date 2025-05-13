# ♾️ Infinite Variance in Reinforcement Learning

This project explores the problem of **infinite variance** in Monte Carlo (MC) methods used in reinforcement learning. It demonstrates how variance can become unbounded in certain environments and evaluates techniques to mitigate this issue.

## 📌 Overview

Monte Carlo methods estimate value functions by averaging sampled returns. However, in some settings, the variance of these returns can become infinite, especially with certain exploration strategies or reward structures.

This project sets up a custom environment that induces infinite variance and investigates:

- The mathematical cause of high variance
- The effect on learning performance
- Strategies to reduce variance (e.g., importance sampling with truncation, baselines)

## 🧠 Topics Covered

- Infinite variance in MC estimates
- Off-policy learning and importance sampling
- Weighted vs. ordinary importance sampling
- Truncated returns and variance control
- Baseline subtraction in policy gradients
