#  🌟 Reinforcement Learning — Full Project Collection (22 Projects)

Welcome to the **Reinforcement-Learning** repository by **Meri-07m**.  
This repository contains **22 complete reinforcement learning projects**, each exploring a different core idea, environment, or limitation of RL.  
It is designed for **students, researchers, and engineers** who want to understand RL deeply through practical experiments.

This is one of the most complete collections of classic RL problems, organized cleanly and consistently.

---

## 📘 What’s Inside?

This repository covers a full range of RL techniques:

- Dynamic Programming (DP)  
- Monte Carlo (MC)  
- Temporal-Difference (TD) learning  
- Eligibility Traces (TD-λ)  
- SARSA / Expected SARSA  
- Q-Learning / Double Q-Learning  
- Maximization Bias  
- Function Approximation  
- Tile Coding / Coarse Coding  
- Multi-Armed Bandits  
- Markov Decision Processes (MDP)  
- Exploration strategies  
- Value function visualization  
- Policy evaluation & improvement  

Each project folder includes separate code, examples, and many include graphs or visualization tools.

---

# 📂 List of All 22 Projects (Detailed Descriptions)


## **1. `access-control`**
A queueing environment that models service acceptance decisions.  
**Key concepts:**
- RL applied to resource allocation problems  
- Stochastic arrival and service processes  
- Balancing acceptance vs rejection decisions  
- Demonstrates policy optimization in queue systems  

---

## **2. `blackjack`**
Monte Carlo prediction and control in a simple card game.  
**Key concepts:**
- First-visit and every-visit Monte Carlo  
- Exploring starts vs. ε-greedy control  
- Policy evaluation for stochastic games  
- Shows how value functions improve over time  

---

## **3. `cliff-walking`**
Classic gridworld with a dangerous cliff region.  
**Key concepts:**
- SARSA (on-policy) vs Q-Learning (off-policy)  
- Risk-sensitive vs risk-seeking behavior  
- Episodic tasks with negative terminal rewards  
- Perfect for visualizing exploration challenges  

---

## **4. `coarse-coding`**
Approximating value functions in continuous spaces.  
**Key concepts:**
- Tile coding / Coarse coding techniques  
- Generalization across similar states  
- Q-learning with function approximation  
- Supports large-scale RL problems  

---

## **5. `counter-examples`**
Environments designed to break or confuse RL algorithms.  
**Key concepts:**
- Failure cases for Q-Learning/SARSA  
- Convergence problems  
- Reward structure edge cases  
- Understanding algorithm weaknesses  

---

## **6. `gambler-problem`**
A probability-based DP example with discrete bets.  
**Key concepts:**
- Value Iteration for DP  
- Optimal staking strategies  
- Terminal absorbing states  
- Classic example from Sutton & Barto  

---

## **7. `gridworld-dp`**
Gridworld solved entirely with Dynamic Programming.  
**Key concepts:**
- Value Iteration  
- Policy Iteration  
- Deterministic transitions  
- Visual value function tables  

---

## **8. `gridworld-mdp`**
Generalized MDP version of Gridworld.  
**Key concepts:**
- Full transition matrix modeling  
- Non-deterministic movement  
- Reward shaping  
- Policy evaluation and control  

---

## **9. `infinite-variance`**
Explores environments where reward variance is enormous.  
**Key concepts:**
- Why MC methods fail with infinite variance  
- Instability in returns  
- Heavy-tailed distributions  
- Motivates variance reduction techniques  

---

## **10. `mazes`**
Agents navigate mazes using RL.  
**Key concepts:**
- Q-Learning / SARSA pathfinding  
- Heatmaps for state visitation  
- Trajectory plotting  
- Handling dead ends + long horizons  

---

## **11. `maximization-bias`**
Shows the overestimation problem in Q-Learning.  
**Key concepts:**
- Demonstrates maximization bias  
- Introduces Double Q-Learning  
- Noise-sensitive value updates  
- Explains why Double Q-Learning improves stability  

---

## **12. `mountain-car`**
Underpowered car trying to climb a hill using momentum.  
**Key concepts:**
- Sparse reward problems  
- Continuous state space  
- TD control methods  
- Motivation for function approximation  

---

## **13. `mountain-car-et`**
Mountain Car enhanced with eligibility traces.  
**Key concepts:**
- TD(λ)  
- Faster convergence  
- Multi-step bootstrapping  
- Shows effect of different λ values  

---

## **14. `random-walk`**
Classic symmetric random walk.  
**Key concepts:**
- MC vs TD prediction  
- One-step bootstrapping  
- Value function learning curves  
- Small environment for theoretical study  

---

## **15. `random-walk-et`**
Random walk extended with eligibility traces.  
**Key concepts:**
- TD(λ) return estimation  
- Weighting multi-step returns  
- Demonstrates λ sensitivity  

---

## **16. `random-walk-fa`**
Random walk with function approximation.  
**Key concepts:**
- Linear value function approximation  
- Replaces tabular methods  
- Good for understanding generalization  

---

## **17. `random-walk-ntd`**
Natural gradient TD methods.  
**Key concepts:**
- Second-order optimization  
- Natural TD updates  
- Improved learning stability  
- Modern extension of classic TD  

---

## **18. `ten-armed-testbed`**
Complete multi-armed bandit testbed.  
**Key concepts:**
- ε-greedy  
- Softmax (Boltzmann exploration)  
- Upper Confidence Bound (UCB)  
- Optimistic initial values  
- Non-stationary reward distributions  

---

## **19. `tic-tac-toe`**
RL agent learns the full game of Tic-Tac-Toe.  
**Key concepts:**
- State-value vs action-value learning  
- Exploring starts  
- Tabular control  
- Shows how RL discovers optimal strategies  

---

## **20. `trajectory-sampling`**
Return estimation through trajectory sampling.  
**Key concepts:**
- Full vs partial trajectory sampling  
- Bias/variance tradeoff  
- Monte Carlo estimation behavior  
- Important for episodic tasks  

---

## **21. `updates-comparison`**
Compares the most common RL update rules.  
**Key concepts:**
- Q-Learning vs SARSA vs Expected SARSA  
- Double Q-Learning  
- Off-policy vs on-policy  
- Stability and convergence analysis  

---

## **22. `windy-gridworld`**
Gridworld with upward “wind” affecting movement.  
**Key concepts:**
- SARSA exploration behavior  
- Episodic learning with turbulence  
- Real-time path improvements  
- Visual movement under wind forces  

---

