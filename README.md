# Value Function and Policy Estimations using RL Techniques

### By Adejoke Adeoye and Cephas Acquah Forson

## Table of Contents
- [Introduction](#introduction)
- [Project Environment](#project-environment)
- [ Project Structure](#project-structure)
- [Techniques](#techniques)
  - [Bellman Optimality Equation](#bellman-optimality-equation)
  - [Policy Iteration](#policy-iteration)
  - [Value Iteration](#value-iteration)
- [Results](#results)
- [Conclusion](#conclusion)

## Introduction
This project focuses on solving a grid world problem using various reinforcement learning techniques. The grid world is a classic environment used in reinforcement learning where an agent navigates a grid to reach certain goals or avoid obstacles and to maximize cumulative rewards. In this project, the aim is to find the optimal policy for the agent by employing three distinct techniques: explicitly solving the Bellman optimality equation, policy iteration with iterative policy evaluation, and value iteration.

## Project Environment
Each cell in the 5 × 5 grid represents a distinct state of the grid world ( defined in the function `grid_plot()`). An agent within this environment can move up, down, left, or right. If the agent attempts to step off the grid, it remains in the same position, resulting in a reward of −0.5. Moving between white squares yields 0 rewards. The grid includes special states (blue, green, red, and yellow squares) that introduce unique behaviors and rewards describes as follows:

- The Blue state at (0, 1) yields a reward of 5 and jumps to the red state at (4, 2).
- The Green state at (0, 4) yields a reward of 2.5 and jumps to either the red state at (4, 2) or the yellow state at (4, 4) with equal probability.
- The agent receives a reward of -0.5 for attempting to move off the grid.

## Project Structure

The project consists of the following files:

- `GridWorldProblem.ipynb`: Jupyter Notebook containing the implementation of RL techniques for the grid world problem.

## Setup
### Requirements
To run the code, you need the following Python packages:
- numpy
- matplotlib

You can install the required packages using:
```bash
pip install numpy matplotlib
```

## Techniques

#### Bellman Optimality Equation
We derive a system of linear equations from the Bellman optimality equation and solve it to find the optimal value function. This method provides a direct approach to determining the optimal policy.

#### Policy Iteration
This method involves iteratively evaluating a given policy and improving it until the policy becomes stable. Policy iteration alternates between policy evaluation, where the value function is computed for a fixed policy, and policy improvement, which is updated based on the current value function.

#### Value Iteration
Combines the processes of policy evaluation and improvement into a single step, iteratively updating the value function until convergence. This method is often more efficient than policy iteration and can handle larger state spaces effectively.

## Results

## Conclusion
All three methods (explicitly solving the Bellman optimality equation, policy iteration, and value iteration) produced similar optimal policies. This consistency is expected as all methods are grounded in the principles of Bellman’s equations. The optimal policies derived from each approach guide the agent towards maximizing cumulative rewards by strategically navigating the grid world environment.


