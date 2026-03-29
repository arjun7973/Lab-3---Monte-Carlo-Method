# Lab 3 - Reinforcement Learning  

## Monte Carlo Control in Blackjack (Blackjack-v1)

---

## Overview

This project implements **first-visit Monte Carlo (MC) control with ε-soft policies** in the Gymnasium Blackjack environment.

### This project contains:

#### 1. Monte Carlo Control (Blackjack-v1)
- Implements **on-policy first-visit MC control**
- Learns action-value function \( Q(s,a) \) from episodic experience
- Uses **ε-greedy policy** for exploration
- Trains over **500,000 episodes**
- Experiments with:
  - Fixed ε (ε = 0.1)
  - Decaying ε schedule

#### 2. Evaluation & Visualization
- 3D **value function plots**:
  - Usable Ace
  - Non-usable Ace
- **Learning curves** (smoothed rewards)
- Comparison between:
  - Fixed exploration
  - Decaying exploration

---

## Environment

- **Environment:** Blackjack-v1 (Gymnasium)
- **State Space:**  
  `(player_sum, dealer_card, usable_ace)` (discrete)
- **Action Space:**  
  - 0 → Stick  
  - 1 → Hit  
- **Rewards:**  
  - +1 → Win  
  - 0 → Draw  
  - -1 → Loss  

---

## Algorithm

- **First-Visit Monte Carlo Control**
- **On-policy learning**
- **ε-soft policy (ε-greedy)**
- Returns computed by **backward traversal of episodes**
- Q-values updated via **sample averaging**

---

## Experimental Setup

- Episodes: **500,000**
- Discount factor: **γ = 1.0**
- Exploration:
  - Fixed ε = 0.1
  - Decay: ε → 0.01
- Learning evaluation:
  - Average reward per episode
  - Smoothed learning curves

---

## Key Results

- MC control learns a **near-optimal Blackjack strategy**
- **ε decay improves convergence**:
  - Smoother value functions
  - Higher average rewards
- Fixed ε maintains exploration but slows convergence

---

## Setup

### Install dependencies:
```python
%pip install numpy matplotlib gymnasium tqdm
