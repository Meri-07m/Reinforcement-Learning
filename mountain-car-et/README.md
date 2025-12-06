# 🚗 Mountain Car — Eligibility Traces (TD(λ))

This folder is part of the **Reinforcement-Learning** repository by **Meri-07m**.  
It contains an in-depth implementation and experimental analysis of **eligibility traces (TD(λ))** applied to the classic **Mountain Car** control problem. This module explores how multi-step backups and traces accelerate learning in a continuous control task, how λ shapes learning behavior, and how trace-based methods connect to modern multi-step algorithms.

---

## 🌍 Overview

The **Mountain Car** problem is a classic reinforcement learning benchmark where an underpowered car must learn to climb a steep hill. Because the engine cannot drive directly to the goal, the agent must first reverse to build momentum — a challenge that tests delayed reward handling and credit assignment.

This folder extends the Mountain Car environment with eligibility trace methods, including:

- Semi-gradient TD(λ)
- SARSA(λ)
- True Online TD(λ)
- Actor–Critic with eligibility traces

The goal is to demonstrate how traces propagate credit backward through time and how λ controls the balance between Monte-Carlo–style long-term updates and TD–style one-step updates.

---

## 🎯 Key Objectives

- Implement trace-based RL algorithms for Mountain Car.
- Compare accumulating, replacing, and true-online traces.
- Analyze the effect of λ on sample efficiency and stability.
- Visualize:
  - learning curves  
  - value/advantage estimates  
  - eligibility trace activations
- Explore feature representations (tile coding, coarse coding, RBFs).

---

## ⚙️ Environment

**Environment:** `MountainCar-v0`  

**State:** 2D continuous  
- Position  
- Velocity  

**Actions:**  
- `0`: push left  
- `1`: no push  
- `2`: push right  

**Reward:** −1 per timestep until reaching goal  
**Goal:** position ≥ 0.5  
**Discount factor γ:** typically 0.99  

---

## 🧩 Algorithms Included

- Semi-Gradient TD(λ)
- SARSA(λ) (on-policy control)
- True Online TD(λ)
- Actor–Critic with eligibility traces

Each algorithm includes backwards-view trace updates and forward-view equivalence tests.

---

## 🧮 Mathematical Summary

### **TD Error**

\[
\delta_t = r_{t+1} + \gamma \hat{V}(s_{t+1}) - \hat{V}(s_t)
\]

---

### **Accumulating Eligibility Traces**

\[
e_t = \gamma\lambda e_{t-1} + \nabla_w \hat{V}(s_t)
\]

\[
w_{t+1} = w_t + \alpha \, \delta_t \, e_t
\]

---

### **Replacing Traces** *(good for tile coding)*

\[
e_{t,i} =
\begin{cases}
1, & i \in \text{active features} \\
\gamma\lambda e_{t-1,i}, & \text{otherwise}
\end{cases}
\]

---

### **True Online TD(λ)**

Implements the stable forward-view–equivalent online method from **van Seijen & Sutton (2014)**.

---

## 🔧 Feature Representations

This folder supports several feature encodings:

### **Tile Coding (Coarse Coding)**
Efficient, high-dimensional, ideal for continuous control.

### **Radial Basis Functions (RBFs)**
Smooth approximation using Gaussian kernels.

### **Neural Network Features**
Optionally used with trace-based last-layer updates.

---

## 📊 Experiments & Analyses

Typical experiments implemented in this folder include:

---

### **1. λ Sweep**
- Compare λ ∈ {0.0, 0.3, 0.5, 0.7, 0.9, 1.0}
- Evaluate episode length and return trends.

---

### **2. Feature Comparison**
- Tile Coding vs RBF vs Neural Network features.

---

### **3. Replacing vs Accumulating Traces**
- Impact on stability and speed of convergence.

---

### **4. Value Surface & Trace Heatmaps**
- Over the state space (position, velocity)
- Shows how eligibility builds and decays along trajectories.

---

## 🔍 Practical Notes

- Scale your continuous inputs before applying tile coding or RBFs.
- **True Online TD(λ)** is often more stable than accumulating traces.
- Higher λ means:
  - More Monte-Carlo-like updates  
  - Higher variance  
  - Requires smaller α
- **Tile coding + replacing traces** is a strong and stable baseline for Mountain Car.

---

## 🧠 Theory Connections

Eligibility traces connect:

- **TD(0)** (λ = 0)  
- **Monte Carlo** (λ = 1)

They form the foundation for modern multi-step algorithms such as:

- **GAE (Generalized Advantage Estimation)**
- **Retrace(λ)**
- **V-trace**

---

## 📚 References

- Sutton & Barto (2018), *Reinforcement Learning: An Introduction*  
- van Seijen & Sutton (2014), *True Online TD(λ)*  
- Mountain Car environment documentation (OpenAI / Gymnasium)

---
