# ⚠️ Counter Examples — Reinforcement Learning

This folder is part of the **[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by **[Meri-07m](https://github.com/Meri-07m)**.  
It focuses on **counterexamples in reinforcement learning (RL)** — specific scenarios or environments that demonstrate the **failure modes of common RL algorithms** such as TD(λ), Q-learning, or function approximation.

---

## 🌍 Overview

While most reinforcement learning algorithms work well under certain assumptions, there exist well-known **counterexamples** that expose their **limitations, instability, or divergence**.  
This module collects and illustrates several such examples, providing valuable insights into **why and when standard algorithms fail**, and how their assumptions break down.

The counterexamples serve as **diagnostic tools** for understanding the **mathematical boundaries** of RL methods — essential for students, researchers, and practitioners who want to design **robust and reliable learning systems**.

---

## ⚡ Key Themes

- 💥 **Divergence with Function Approximation**  
  When using **nonlinear or off-policy updates**, methods like **Q-learning** can diverge even in simple MDPs.

- 🔁 **Off-Policy Instability**  
  Demonstrates that **off-policy TD learning** can fail when the target and behavior policies differ too much.

- 🧮 **Bias and Variance Issues**  
  Shows how certain reward structures or step sizes lead to oscillation, bias, or extremely slow convergence.

- 📊 **Illustrative Simulations**  
  Each example includes visualizations of **learning curves**, **value function behavior**, and **error divergence**.

---

## 🧩 Example Scenarios

1. **Baird’s Counterexample (Star Problem)**  
   - A famous demonstration where **off-policy TD(0)** with linear function approximation diverges.  
   - The agent updates value estimates for a set of states shaped like a “star,” where one central state transitions probabilistically to outer states.  
   - Despite bounded rewards and a simple structure, value estimates blow up — proving TD can diverge.

2. **Non-Markov Reward Dependencies**  
   - Illustrates how violating the Markov property breaks learning guarantees.  
   - Useful for testing model robustness and assumption sensitivity.

3. **Function Approximation Instability**  
   - Examples using linear or polynomial features that lead to oscillations in Q-values.  
   - Helps visualize how **representation design** affects convergence.

4. **Off-policy Divergence in Control**  
   - Shows how **Q-learning** diverges when exploration and target policies differ too much.  
   - Reinforces the importance of **policy consistency** in value iteration.

---

## 🧠 Learning Objectives

These counterexamples demonstrate:

- When and why **TD methods** (like TD(0) or Q-learning) fail to converge.  
- The distinction between **on-policy** and **off-policy** learning stability.  
- How **function approximation** introduces additional risks in learning.  
- Why careful **feature design**, **step-size tuning**, and **policy constraints** matter in practice.

---

## ⚙️ Implementation Details

Each example includes:

- A **custom MDP environment** with minimal state/action space.  
- **Agent implementations** for TD(0), Q-learning, or SARSA.  
- Visualization of:
  - Value divergence over time  
  - Parameter magnitude growth  
  - Comparison with theoretical expectations  

