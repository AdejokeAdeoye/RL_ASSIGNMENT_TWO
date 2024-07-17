# Value Function and Policy Estimations using RL Techniques

### By Adejoke Adeoye and Cephas Acquah Forson

## Table of Contents
- [Introduction](#introduction)
- [Project Environment](#project-environment)
- [Methodology](#methodology)
  - [Estimating the Value Functions](#estimating-the-value-functions)
  - [Estimating the Policy Functions](#estimating-the-policy-functions)
- [Conclusion](#conclusion)

## Introduction
This project focuses on solving a grid world problem using various reinforcement learning techniques. The grid world is a classic environment used in reinforcement learning where an agent navigates a grid to reach certain goals or avoid obstacles and to maximize cumulative rewards. In this project, the aim is to find the optimal policy for the agent by employing three distinct techniques: explicitly solving the Bellman optimality equation, policy iteration with iterative policy evaluation, and value iteration.

## Project Environment
Each cell in the 5 × 5 grid represents a distinct state of the grid world. An agent within this environment can move up, down, left, or right. If the agent attempts to step off the grid, it remains in the same position, resulting in a reward of −0.5. Moving between white squares yields 0 rewards. The grid includes special states (blue, green, red, and yellow squares) that introduce unique behaviors and rewards describes as follows:

- The Blue state at (0, 1) yields a reward of 5 and jumps to the red state at (4, 2).
- The Green state at (0, 4) yields a reward of 2.5 and jumps to either the red state at (4, 2) or the yellow state at (4, 4) with equal probability.
- The agent receives a reward of -0.5 for attempting to move off the grid.

### Python Function for Bellman Optimality Equation
- `bellman_optimality_eq(env, gamma=0.9)`

## Policy Iteration
Policy iteration involves two main steps: policy evaluation and policy improvement.

1. **Policy Evaluation**: Evaluate the value function \( V^\pi(s) \) for a given policy \( \pi \):

\[ V^\pi(s) = \sum_{a} \pi(a|s) \sum_{s'} P(s'|s,a) \left[ R(s,a,s') + \gamma V^\pi(s') \right] \]

2. **Policy Improvement**: Improve the policy by acting greedily with respect to the value function:

\[ \pi'(s) = \arg\max_a \sum_{s'} P(s'|s,a) \left[ R(s,a,s') + \gamma V^\pi(s') \right] \]

### Python Functions for Policy Iteration
- `policy_iteration(env, gamma=0.9)`

## Value Iteration
Value iteration updates the value function directly using the Bellman optimality equation:

\[ V(s) \leftarrow \max_a \sum_{s'} P(s'|s,a) \left[ R(s,a,s') + \gamma V(s') \right] \]

This process is repeated until the value function converges.


## Conclusion
All three methods (explicitly solving the Bellman optimality equation, policy iteration, and value iteration) produced similar optimal policies. This consistency is expected as all methods are grounded in the principles of Bellman’s equations. The optimal policies derived from each approach guide the agent towards maximizing cumulative rewards by strategically navigating the grid world environment.


