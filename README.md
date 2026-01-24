# WiDS Project

This repository contains my work for the **Winter in Data Science (WiDS)** program, completed over four weeks. The project focuses on building strong foundations in Python, reinforcement learning, and their application to decision-making and trading environments.

---

## Submission (Weeks 1–3)

During the first three weeks, I focused on developing core technical skills and understanding fundamental concepts in reinforcement learning and data analysis.

### Tools and Libraries

* Learned to use **Python** for scientific computing
* Worked with the following libraries:

  * **NumPy** for numerical computations
  * **Pandas** for data manipulation and analysis
  * **Matplotlib** for data visualization

### Multi-Armed Bandit Problem

Implemented and compared the following action-selection strategies:

* **Greedy**
* **Epsilon-Greedy**
* **Upper Confidence Bound (UCB)**

These methods were evaluated to study the exploration–exploitation trade-off.

### Reinforcement Learning Theory

* Studied fundamental concepts from *Reinforcement Learning: An Introduction* by **Sutton & Barto**
* Understood rewards, policies, value functions, and environment modeling

### Markov Decision Processes (MDPs)

Modeled the following environments as MDPs:

* Bandit Walk
* Slippery Walk
* Frozen Lake

Additionally, automated the construction of MDPs using Python to generalize state transitions and reward structures.

### Financial Data and Trading Basics

* Learned common financial market terms such as **Open**, **Close**, and **Adjusted Close**
* Implemented a **simple moving average–based trading strategy**
* Analyzed historical stock price data using Pandas

### Development Practices

* Learned to use **GitHub** for version control and project management
* Used **Markdown** to document the project and create this README

---

## Final Submission (Week 4)

In the final week, I implemented a complete **reinforcement learning–based trading agent** using **Q-Learning**, starting from raw market data to evaluation against a baseline strategy.

### Project: Reinforcement Learning Based Trading Agent

The notebook follows a full pipeline:

1. Download historical stock price data
2. Build a custom trading environment
3. Train a Q-Learning agent
4. Evaluate performance
5. Compare with a buy-and-hold baseline

### Trading Environment Design

A custom `TradingEnv` class was implemented to simulate stock trading:

* **State**: derived from the current time step and market price information

* **Actions**:

  * Buy
  * Sell
  * Hold

* **Initial capital**: 100,000

* **Reward**: total portfolio value

  [ cash + (stocks_held × current_price) ]

* **Episode termination**: end of the price series

This formulation allows the agent to learn directly from interaction with the market sequence.

### Q-Learning Setup

* Implemented a **Q-table–based** approach for discrete state–action values

* Used **ε-greedy exploration** (ε = 0.1)

* Updated values using the Bellman equation:

  [ Q(s,a) ← Q(s,a) + α ( r + γ max_a' Q(s',a') − Q(s,a) ) ]

* Tuned learning rate and discount factor for stable learning

### Training

* Ran multiple episodes over the same price series
* At each step:

  * Selected an action using ε-greedy policy
  * Executed it in the environment
  * Observed next state and reward
  * Updated the Q-table

### Evaluation

* Tested the trained agent on the same market data
* Tracked:

  * Portfolio value over time
  * Final profit

### Baseline Comparison

Implemented a **buy-and-hold strategy** as a benchmark and compared it with the learned policy to evaluate whether reinforcement learning produced superior trading behavior.

### Key Learning Outcomes

* Practical implementation of Q-Learning
* Designing custom RL environments
* Connecting Bellman equations to real code
* Understanding limitations of simple tabular RL in financial markets

---

## Summary

This project covers:

* Python-based data analysis
* Reinforcement learning fundamentals
* Bandit algorithms and MDP modeling
* Algorithmic trading strategies
* Q-Learning–based decision making

It reflects a complete learning pipeline from basic tools to applying advanced RL methods in real-world–inspired environments.

