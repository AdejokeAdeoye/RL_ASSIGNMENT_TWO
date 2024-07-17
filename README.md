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
  - [Monte Carlo Method with Exploring Starts](#Monte-Carlo-Method-with-Exploring-Starts)
  - [Monte Carlo Method with ϵ-Soft Policy](#Monte-Carlo-Method-with-ϵ-Soft-Policy)
  - [Behavior Policy with Importance Sampling](#Behavior-Policy-with-Importance-Sampling)
  - [Policy Iteration with State Permutations](#Policy-Iteration-with-State-Permutations)
- [Results](#results)
- [Conclusion](#conclusion)

## Introduction
This project focuses on solving a grid world problem using various reinforcement learning techniques. The grid world is a classic environment used in reinforcement learning where an agent navigates a grid to reach certain goals or avoid obstacles and to maximize cumulative rewards. In this project, the aim is to find the optimal policy for the agent by employing three distinct techniques: explicitly solving the Bellman optimality equation, policy iteration with iterative policy evaluation, and value iteration.

## Project Environment
Each cell in the 5 × 5 grid represents a distinct state of the grid world ( defined in the function `grid_plot()`). An agent within this environment can move up, down, left, or right. If the agent attempts to step off the grid, it remains in the same position, resulting in a reward of −0.5. Moving between white squares yields 0 rewards. The grid includes special states (blue, green, red, and yellow squares) that introduce unique behaviors and rewards describes as follows:

- The Blue state at (0, 1) yields a reward of 5 and jumps to the red state at (4, 2).
- The Green state at (0, 4) yields a reward of 2.5 and jumps to either the red state at (4, 2) or the yellow state at (4, 4) with equal probability.
- The agent receives a reward of -0.5 for attempting to move off the grid.

In part 2, the environment has been modified to include two terminal states defined at (4, 0) and (2, 4), where the episode terminates upon reaching these states, with a reward of 0. Also, in this part, the agent receives a reward of -0.2 for moving between white cells, and a reward of -0.5 for attempting to move off the grid.


## Project Structure

The project consists of the following files:

- `GridWorldProblem.ipynb`: Jupyter Notebook containing the implementation of RL techniques for the grid world problem.
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
#### Value Function
1. **Explicitly Solving the Bellman Optimality Equation**
Row 0 column 1 corresponding to the blue special state and row 0 column 4 have the highest value functions. Below are the results of the entire grid (all 25 states).
2. **Policy Iteration**
Row 0 column 1 corresponding to the blue special state and row 0 column 4 have the highest value functions.
3. **Value Iteration**
This is similar to the that of policy iteration, row 0 column 1 corresponding to the blue special state has the highest value function.
#### Policy Functions
The optimal policy is derived by solving the Bellman optimality equations and determining the action that maximizes the value function for each state.
1. **Explicitly Solving the Bellman Optimality Equation**
The resulting policy function is consistent with the expected behavior, directing the agent towards states with higher rewards.
2. **Policy Iteration**
This produced an optimal policy that aligns closely with the results obtained from explicitly solving the Bellman equations. Here, the technique ensures that the policy converges to the optimal strategy, emphasizing actions that lead to higher cumulative rewards.
3. **Value Iteration**
This yielded an optimal policy that is similar to those obtained from the other methods.

#### Monte Carlo Method with Exploring Starts
The optimal policy derived using the Monte Carlo Method with Exploring Starts method showed a clear preference for actions that led the agent to high-reward states (blue and green) while avoiding terminal states. Value function visualizations indicated higher values around the special states, confirming the effectiveness of the policy.

#### Monte Carlo Method with ϵ-Soft Policy
The epsilon-soft approach resulted in a more exploratory policy, ensuring that all actions were sufficiently explored. The resulting policy was slightly different, but still converged towards favoring high-reward actions.

#### Behavior Policy with Importance Sampling
The use of importance sampling weights allowed for effective policy learning even with a behavior policy. The optimal policy closely matched that obtained from the on-policy methods, validating the approach.

#### Policy Iteration with State Permutations
The policy iteration method considering state permutations resulted in a more robust policy that could adapt to the dynamic environment. The value function showed a smoother gradient, reflecting the agent’s adaptability to the stochastic changes in the environment.

## Conclusion
In part 1, All three methods (explicitly solving the Bellman optimality equation, policy iteration, and value iteration) produced similar optimal policies. This consistency is expected as all methods are grounded in the principles of Bellman’s equations. The optimal policies derived from each approach guide the agent towards maximizing cumulative rewards by strategically navigating the grid world environment.

In the second part of the analysis, The Monte Carlo methods, both with exploring starts and epsilon-soft approaches, provided reliable policies by ensuring sufficient exploration. The off-policy control method effectively utilized importance sampling to learn from a behaviour policy. The policy iteration with state permutations highlighted the importance of adaptability in dynamic environments, leading to a robust policy that could handle stochastic changes.


