# TD(0) Control Comparison on CartPole

## Overview

This project compares three tabular Temporal-Difference control algorithms on the `CartPole-v1` environment:

- SARSA
- Q-learning
- Expected SARSA

Because CartPole has a continuous state space, the four state variables are discretized into bins so that each algorithm can learn using a Q-table.

## Algorithms

### SARSA

SARSA is an on-policy TD control algorithm. Its update uses the next action selected by the current epsilon-greedy policy.

### Q-Learning

Q-learning is an off-policy TD control algorithm. Its update uses the maximum estimated Q-value of the next state.

### Expected SARSA

Expected SARSA uses the expected next-state Q-value under the epsilon-greedy policy rather than relying on a single sampled next action.

## Training Configuration

- Environment: `CartPole-v1`
- Training episodes: 3,000
- Maximum steps per episode: 500
- Learning rate: 0.1
- Discount factor: 0.99
- Initial epsilon: 1.0
- Minimum epsilon: 0.05
- Epsilon decay: 0.997

## Evaluation

All three algorithms are evaluated using the same 20 test environment seeds to provide a consistent comparison.

## Results

| Algorithm | Average Test Reward |
|------------|--------------------:|
| SARSA | 136.90 |
| Q-learning | 80.60 |
| Expected SARSA | 43.95 |

Under the selected discretization and hyperparameters, SARSA achieved the highest average test reward.

The results are specific to this experimental configuration and should not be interpreted as a general ranking of the three TD control algorithms.

## Technologies

- Python
- NumPy
- Gymnasium
- Matplotlib

## Key Concepts

- Reinforcement Learning
- Temporal-Difference Learning
- SARSA
- Q-Learning
- Expected SARSA
- Epsilon-Greedy Exploration
- State Discretization
- Tabular Q-Learning
