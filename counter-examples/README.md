# ⚠️ Counter-Examples — Reinforcement Learning

This folder is part of the **[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by **[Meri-07m](https://github.com/Meri-07m)**.  
It contains **counter-example environments and simulations** that illustrate failure modes of standard reinforcement learning algorithms, especially when using function approximation and off-policy updates.

---

## 🌍 Overview

While many RL algorithms converge under ideal conditions, there are important **counter-examples** that expose their limitations. These examples help us understand how combining certain ingredients — even in very simple systems — can lead to divergence or instability.

This module is focused on these pathological cases. By studying them, you can gain a deeper intuition about:

- Why **off-policy TD** can diverge when used with **linear function approximation**.  
- The role of the *“deadly triad”* in reinforcement learning (function approximation + bootstrapping + off-policy). :contentReference[oaicite:0]{index=0}  
- How feature representation and target distribution can destabilize learning.  
- Why some more advanced algorithms (e.g. Gradient TD methods) were developed to **solve** these problems. :contentReference[oaicite:1]{index=1}  

---

## 🔍 Key Example: Baird’s Counter-Example

One of the most famous counter-examples included here is **Baird’s counter-example**, which demonstrates that even very simple reinforcement learning setups can diverge when learning off-policy with function approximation. :contentReference[oaicite:2]{index=2}  

**Setup:**

- There are 7 non-terminal states (6 “upper” states + 1 “lower” state) and 2 actions:  
  - **Dashed** action: from any of the 6 upper states, it moves to one of the other upper states uniformly.  
  - **Solid** action: always moves to the lower (7th) state. :contentReference[oaicite:3]{index=3}  
- **Behavior policy** \(b\): chooses the dashed action with probability \(6/7\), solid with \(1/7\). :contentReference[oaicite:4]{index=4}  
- **Target policy** \(\pi\): always chooses the solid action. :contentReference[oaicite:5]{index=5}  
- **Reward**: always 0 for all transitions. :contentReference[oaicite:6]{index=6}  
- **Discount factor**: typically set very high (e.g. \(\gamma = 0.99\)). :contentReference[oaicite:7]{index=7}  
- **Value function approximation**: linear function approximation is used, with carefully chosen features such that the combination of updates causes divergence. :contentReference[oaicite:8]{index=8}  

**Why It Diverges:**

- Because the updates are *off-policy* (i.e. distribution under \(b\) differs from \(\pi\)), and we use *bootstrapping* (TD), the learned weight vector diverges. :contentReference[oaicite:9]{index=9}  
- Even though the true value function is zero everywhere (since reward is always zero), the semi-gradient TD updates push the weights to grow without bound. :contentReference[oaicite:10]{index=10}  
- Intuitively: the “leakage” of value through shared weights / features causes the updates to amplify, and because not all states are visited under the target policy according to the same distribution, the corrections never properly stabilize. :contentReference[oaicite:11]{index=11}  

---

## 🧠 Learning Objectives

By studying these counter-examples, you will:

1. Understand the **“deadly triad”**:  
   - Function approximation  
   - Bootstrapping  
   - Off-policy learning  
   These three together can cause divergence. 
2. See concretely how **linear function approximation** can be *unstable* in off-policy settings.  
3. Appreciate why newer algorithms (e.g., **Gradient TD**, **TDC**, **GTD2**) were developed — to solve divergence problems. :contentReference[oaicite:13]{index=13}  
4. Gain intuition about the importance of designing stable RL systems (feature choice, policy distribution, step-sizes).

---

## ⚙️ Implementation Details

- **Environments / MDPs**:  
  - Code to simulate Baird’s counter-example (states, transition logic, feature vectors).  
  - Possibly other variants of counter-examples (depending on what you have in the folder).

- **Agents / Algorithms**:  
  - Semi-gradient **TD(0)** (off-policy) — the classical learner that diverges.  
  - Optionally, **Gradient TD** (e.g. GTD2 / TDC) to show a convergent alternative.

- **Visualization**:  
  - Track weight norms (e.g., \(\|w\|\)) over iterations.  
  - Plot divergence behavior.  
  - Compare with more stable methods, if implemented.

