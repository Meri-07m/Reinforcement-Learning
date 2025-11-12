# 🏢 Access Control — Reinforcement Learning

This folder is part of the **[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by **[Meri-07m](https://github.com/Meri-07m)**.  
It explores **reinforcement learning for resource allocation and queue management**, modeled through the **Access Control Queuing Problem** — a classic example demonstrating how RL can optimize dynamic decision-making under constraints.

---

## 🌍 Overview

The **Access Control problem** is a reinforcement learning task where an agent must decide whether to **accept or reject incoming requests** for limited system resources.  
Each request has an associated **priority or reward**, and the system can only handle a certain number of active tasks simultaneously. The objective is to **maximize the long-term average reward** while managing resource capacity efficiently.

This environment highlights **Markov Decision Processes (MDPs)** in practical scheduling and allocation scenarios — similar to real-world applications in **network routing**, **server task scheduling**, and **bandwidth management**.

---

## ⚙️ Problem Description

- The environment consists of a **queue of available resources** (servers, slots, or connections).  
- At each time step:
  - A **new request** arrives with a priority level (e.g., 1–4).  
  - The agent decides whether to **accept** the request (if resources are available) or **reject** it.  
  - If accepted, the request occupies a slot until it’s released after a random duration.  
  - Rewards are tied to the accepted request’s priority.  

The challenge is to **balance acceptance of high-value requests** with **resource availability**, optimizing long-term performance.

---

## 🧩 How It Works

1. **State Representation**  
   The state is typically represented by:
   - The number of **available resources**.  
   - The **priority of the incoming request**.  

   Example: `(available_servers, request_priority)`

2. **Actions**  
   - `0`: Reject the request.  
   - `1`: Accept the request (if capacity allows).  

3. **Reward Function**  
   - Reward equals the **priority value** of accepted requests.  
   - No reward (0) for rejected or impossible actions.

4. **Transition Dynamics**  
   - Accepted requests occupy a server for a random number of steps before freeing it.  
   - Requests arrive randomly at each step.

5. **Learning Algorithm**  
   - Typically solved using **TD control** or **Q-learning**:
     \[
     Q(s, a) \leftarrow Q(s, a) + \alpha \big[r + \gamma \max_{a'} Q(s', a') - Q(s, a)\big]
     \]
   - The learned policy balances **short-term gain (accepting many requests)** with **long-term reward (saving slots for high-priority tasks)**.

---

## ⚡ Key Features

- 🧠 **Dynamic Decision-Making**
  - The agent continuously adapts to resource availability and request patterns.  
  - Demonstrates learning in stochastic and constrained environments.

- 🏗️ **Markov Decision Process Formulation**
  - Explicit modeling of states, actions, and rewards.  
  - Captures the essence of **online resource management** problems.

- 📊 **Visualization and Performance Metrics**
  - Track value function convergence.  
  - Plot learning curves for average reward per episode.  
  - Compare policies (e.g., greedy vs. learned).  

- 🔍 **Extendable Design**
  - Can be extended to continuous state spaces, dynamic request distributions, or function approximation.


