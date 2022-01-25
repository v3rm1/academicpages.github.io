---
title: "Deep Learning: Reinforcement Learning"
excerpt: "Project work for the Deep Learning course offered under the MSc AI program at the University of Groningen"
collection: portfolio
---
[View Project on Github](https://github.com/v3rm1/dl2_rl)

## Introduction

There are a lot of reasons for wanting AI systems to be able to accurately estimate their own confidence, particularly in domains where failure incurs a real world cost.

We have devised an unconventional method of including confidence estimation in a reinforcement learning system which we hypothesize will actually improve performance by forcing the system to develop a more informative model of the state-action space.

The method we propose is to construct a system which, instead of just outputting actions, gives action/confidence pairs, where the confidence is a number between 0 or 1 which represents the system's best guess as to the probability of the action is selected resulting in a successful outcome.

This confidence is then trained by altering the reward function such that the reward is a function of both the real value of the action selected in the environment (success or failure), as well as the confidence given. We want to reward the system for giving a high confidence when it selects actions correctly, and to punish the system for a high confidence when it selects actions poorly.

This change in the reward function will vary the magnitude of punishment and reward, and thus change how the system learns.

---

## Experiment Design

The environment chosen for implementing and testing the algorithms is the Atari Pong environment from
the python Open AI Gym library. The game has a total of 100800 states. It has six different actions,
listed in Table 1. The model plays against the Open AI random adversary, which is part of the library.
The model game state is represented by the game’s pixels, a 210x160x3 array. As a preprocessing
step, this array is first cropped to a 160x160x3 frame with the relevant game information, and then
downsampled to a 80x80x3 array. All of the game information in Pong can be contained in a single
color channel, so the input is then converted to grayscale. Finally, the game’s background color is made
completely black. The resulting array is the input for the model.

We test out two approaches:

1. Proximal Policy Optimization

PPO is part of a family of policy gradient methods, which use stochastic gradient descent to optimize a policy. The PPO algorithm is an improvement over Trust Region Policy Optimization\cite{DBLP:journals/corr/SchulmanLMJA15} (TRPO), utilizing a clipped objective function, removing the KL Divergence penalty found in TRPO. Thus PPO limits the change in policy without computing the KL Divergence at every step, more generalized to continuous control tasks and easier to implement compared to other Policy Optimization algorithms.

2. Proximal Policy Optimization with Confidence Estimation

The Proximal Policy Optimization Actor-Critic network is modified to generate a confidence for every action the actor generates, extending the actor network to a single Dense layer with a Sigmoid activation function, generating a confidence in the policy chosen by the actor. This confidence is then used in computing the reward obtained by the network.

The model achieves an accurate confidence estimation when the estimated confidence is equal to the probability value returned by the Softmax layer of the actor network. This can be achieved by rewarding successes with high confidence while penalizing failure with high confidence. We modify the reward function to achieve this through two functions, returning a maximum reward when estimated confidence equals the actual probability of the action.


