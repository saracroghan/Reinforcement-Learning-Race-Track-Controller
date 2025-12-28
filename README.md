# Reinforcement Learning Racetrack Controller

This repository contains a Python implementation of various Reinforcement Learning (RL) algorithms applied to the "Racetrack" problem. The objective is to train an autonomous agent to navigate from a starting line to a finish line on a grid-based track while managing velocity, acceleration, and wall collisions under stochastic conditions.

## Project Overview

The program models the racetrack as a Markov Decision Process (MDP). The agent must decide on acceleration actions (-1, 0, 1) in both the x and y dimensions to reach the finish line in the minimum number of steps. To ensure a robust policy, the environment includes an 80% success rate for intended acceleration and a 20% chance of engine failure where no acceleration is applied.

### Implemented Algorithms

* **Value Iteration**: An offline dynamic programming approach that iteratively updates state values until convergence to find the optimal policy.
* **Q-Learning**: An off-policy reinforcement learning algorithm that learns the value of the best action for a given state through exploration and exploitation.
* **SARSA (State-Action-Reward-State-Action)**: An on-policy reinforcement learning algorithm that updates Q-values based on the action actually taken by the current policy.

## Technical Features

* **Collision Detection**: Uses **Bresenham's Line Algorithm** to determine if the car's trajectory crosses a wall cell or goes out of bounds between discrete time steps.
* **Crash Recovery Policies**: 
    * **STRT (Reset to Start)**: On a crash, the car's position is reset to the starting line and its velocity is zeroed out.
    * **NRST (Nearest Point)**: On a crash, the car is moved to the nearest valid track cell to the point of impact and its velocity is reset.
* **State and Velocity Constraints**: The car maintains a velocity between -5 and 5 in both dimensions. 
* **Visualization**: Includes a visualization suite using `matplotlib` that generates PNG images showing the track grid and the specific path taken by the agent.

## Prerequisites

The project requires Python 3.x and the following libraries:
* `numpy`
* `matplotlib`

Install the dependencies via pip:
`pip install numpy matplotlib`

## How to Run

The script is controlled by parameters in the main execution block.

1. **Set Parameters**: Update the following variables in the configuration section of the script:
    * **ALGORITHM**: Select from `"ValItr"`, `"QLrng"`, or `"
