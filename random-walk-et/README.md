# 🔁 Random Walk — Eligibility Traces (TD(λ))

This folder is part of the  
**[Reinforcement-Learning](https://github.com/Meri-07m/Reinforcement-Learning)** repository by  
**[Meri-07m](https://github.com/Meri-07m)**.

It contains an **in-depth implementation and analysis** of **Eligibility Traces** applied to the classic **Random Walk** prediction problem.  
This is one of the most important examples in reinforcement learning theory, because it clearly demonstrates:

- how **Temporal Difference** learning works,  
- how **TD(λ)** smoothly unifies TD(0) with Monte-Carlo methods,  
- how **credit assignment** propagates through sequences,  
- and how λ influences the **speed and stability of learning**.

This module functions as both an **educational tutorial** and an **experimental playground** for deeply understanding TD(λ).

---

# 🌍 1. The Random Walk Environment

The classic 7-state random walk is a simple Markov Reward Process first introduced in RL literature as a clean environment to evaluate prediction algorithms.

### 📌 Structure


- There are **5 non-terminal states** (A–E).
- The agent **starts in the middle state** (C).
- At every step:
  - With 0.5 probability → move **left**
  - With 0.5 probability → move **right**
- If the agent reaches:
  - **the right terminal** → reward **+1**
  - **the left terminal** → reward **0**
- The episode ends immediately when a terminal is reached.

Because the reward is only at termination, learning the value function is entirely about learning the **probability of reaching the right terminal from each state**.

---

# 🧠 2. True Values

For a symmetric random walk with start in the middle, the true values are known analytically:

| State | True Value |
|-------|------------|
| A | 1/6 |
| B | 2/6 |
| C | 3/6 |
| D | 4/6 |
| E | 5/6 |

These values are used to compute **RMS error curves**, which are a standard benchmark.

---

# ⚡ 3. Eligibility Traces: The Core Idea

Eligibility traces solve a fundamental problem in RL:

> **How much credit do we assign to earlier states when a TD error happens?**

Without traces, TD(0) gives credit *only* to the immediately preceding state.  
Monte-Carlo methods give credit *uniformly* to all states in the entire trajectory.

Eligibility traces provide a flexible middle ground.

---

# 🔍 4. What TD(λ) Does Conceptually

TD(λ) allocates credit backwards along the history of visited states:

- Recently visited states receive **high credit**
- Older states receive **decaying credit**
- The decay rate is controlled by **λ**

### If λ = 0  
Only the most recent state is updated → **classic TD(0)**

### If λ = 1  
All states in the episode get equal credit → **Monte-Carlo** (every-visit)

### If 0 < λ < 1  
A continuum of trade-offs:  

This dramatically improves learning efficiency.

---

# 🔣 5. Mathematical Details

## 5.1 Eligibility Trace Update

Each state \( s \) has a trace \( e(s) \).  
At timestep t:

### 1️⃣ Increase trace for current state:
\[
e_t(s_t) \leftarrow e_t(s_t) + 1
\]

### 2️⃣ Decay all traces:
\[
e_t(s) \leftarrow \gamma \lambda e_{t-1}(s)
\]

## 5.2 TD Error

\[
\delta_t = r_{t+1} + \gamma V(s_{t+1}) - V(s_t)
\]

## 5.3 Value Update

\[
V(s) \leftarrow V(s) + \alpha \, \delta_t \, e_t(s)
\]

This is the **backward view** of TD(λ).

---

# 🧩 6. Forward View vs Backward View

Eligibility traces have two mathematical perspectives:

### 📌 Forward View  
Think in terms of **multi-step returns**:

\[
G_t^{(n)} = r_{t+1} + \gamma r_{t+2} + \dots + \gamma^{n-1} r_{t+n} + \gamma^n V(s_{t+n})
\]

TD(λ) uses a geometrically-weighted combination of all n-step returns.

### 📌 Backward View  
The computational view:  
- Compute TD errors in real-time  
- Propagate them backward with eligibility traces

The backward view is **efficient** and equivalent to the forward view for linear function approximation.

---

# 🧪 7. Experiments Implemented

This module includes multiple experiments inspired by Sutton & Barto:

---

## 📘 7.1 Experiment: RMS Error Across λ

A fundamental experiment that shows:

- how different λ values affect prediction accuracy,
- measured across many episodes,
- averaged over many independent runs.

The famous result:

> **Intermediate values of λ (around 0.7–0.9) perform best.**

---

## 📘 7.2 Experiment: Sensitivity to α (Learning Rate)

TD(λ) is sensitive to step size.  
For each λ, we test multiple α values and compute the average RMS error.

Result:

- Small λ often allows **larger α**  
- Large λ (close to 1) requires **very small α** for stability

---

## 📘 7.3 Experiment: Value Function Visualization

We generate plots such as:

- true value function
- predicted value function under different λ
- learning curves over episodes
- evolution of state values over time

This helps visualize how trace propagation shapes learning.
                        



