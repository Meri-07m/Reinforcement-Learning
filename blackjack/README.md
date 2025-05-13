# 🃏 Blackjack — Reinforcement Learning

This project implements **Blackjack**, a popular casino card game, as a **Reinforcement Learning** environment. It demonstrates various **model-free** reinforcement learning algorithms, including **Monte Carlo**, **SARSA**, and **Q-learning**, to learn optimal strategies in the game.

The goal is to train an agent to maximize its winnings by using different RL methods to learn an optimal strategy in Blackjack. It can be used as an educational tool for understanding reinforcement learning concepts in a simple and interactive way.

## 📌 Problem Overview

In Blackjack, the goal is to beat the dealer by getting a hand value as close to 21 as possible, without going over. The player and dealer are dealt two cards. The player can choose to "hit" (draw a card) or "stick" (keep their current hand). The dealer must also stick to certain rules (must stand at 17 or higher).

### Key Rules:
- The values of cards are as follows:
  - Number cards (2-10) are worth their face value.
  - Jacks, Queens, Kings are worth 10 points.
  - Aces can be worth either 1 or 11 points, depending on what benefits the hand more.
- If the player's hand value exceeds 21, they lose (bust).
- The dealer must keep drawing cards until their hand value is at least 17.
- The game ends when the player or the dealer wins, or the player chooses to quit.

## 🧠 Reinforcement Learning Algorithms Implemented

This project demonstrates several key **model-free reinforcement learning** techniques:

### 1. **Monte Carlo Method**
- The Monte Carlo method is used for estimating the value of actions based on the average return from complete episodes.
- This method doesn't require a model of the environment and instead learns the value of state-action pairs by observing the outcomes of actions over multiple episodes.
  
### 2. **SARSA (State-Action-Reward-State-Action)**
- **SARSA** is an on-policy temporal difference learning algorithm.
- It updates the action-value function (Q-values) based on the agent’s current state, action, reward, and next state-action pair.
- This method ensures that the policy is being updated during the agent's learning process.

### 3. **Q-learning**
- **Q-learning** is an off-policy temporal difference learning algorithm.
- The key difference from SARSA is that Q-learning learns the value of state-action pairs by updating Q-values using the best possible action at the next state (regardless of the agent's current policy).
- This results in an exploration-exploitation tradeoff, where the agent exploits the learned Q-values to maximize its rewards.

