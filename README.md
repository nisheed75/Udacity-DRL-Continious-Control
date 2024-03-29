# Udacity-DRL-Continuous-Control

![Picture of the environment](https://github.com/nisheed75/Udacity-DRL-Continious-Control/blob/master/images/environement.gif)

# DRL - DDPG Algorithm - Reacher Continuous Control
Udacity Deep Reinforcement Learning Nanodegree Program - Reacher Continuous Control

## Introduction
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to the position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### The Environment
For this project, we will provide you with two separate versions of the Unity environment:

    The first version contains a single agent.
    The second version contains 20 identical agents, each with its copy of the environment.

The second version is useful for algorithms like PPO, A3C, and D4PG that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience. 


### Project Objectives
Note that your project submission need only solve one of the two versions of the environment.
Option 1: Solve the First Version

The task is episodic, and to solve the environment, your agent must get an average score of +30 over 100 consecutive episodes.
Option 2: Solve the Second Version

The barrier to solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and overall agents). Specifically,

    After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
    This yields an average score for each episode (where the average is over all 20 agents).

As an example, consider the plot below, where we have plotted the average score (overall 20 agents) obtained with each episode

![Udacity Results](https://github.com/nisheed75/Udacity-DRL-Continious-Control/blob/master/images/udacity_solution.png)


The environment is considered solved when the average (over 100 episodes) of those average scores is at least +30. In the case of the plot above, the environment was solved at episode 63, since the average of the average scores from episodes 64 to 163 (inclusive) was greater than +30.

## Getting Started:

### Unity Environment
Unity Machine Learning Agents (ML-Agents) is an open-source Unity plugin that enables games and simulations to serve as environments for training intelligent agents.

For game developers, these trained agents can be used for multiple purposes, including controlling NPC behavior (in a variety of settings such as multi-agent and adversarial), automated testing of the game builds and evaluating different game design decisions pre-release.

In this course, you will use Unity's rich environments to design, train, and evaluate your own deep reinforcement learning algorithms. You can read more about ML-Agents by perusing the [GitHub repository](https://github.com/Unity-Technologies/ml-agents).

### Requeriments:
- tensorflow: 1.7.1
- Pillow: 4.2.1
- matplotlib
- numpy: 1.11.0
- pytest: 3.2.2
- docopt
- pyyaml
- protobuf: 3.5.2
- grpcio: 1.11.0
- torch: 0.4.1
- pandas
- scipy
- ipykernel
- jupyter: 5.6.0

### Running the code

After you install the unity agent following these [instructions] (https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Readme.md), start your jupyter notebook and open the Continuous_Control.ipynb solution notebook and execute each cell.

## The solution:
* The solution for this project was an implementation of the Deep Deterministic Policy Gradients algorithm.
* This project was challenging is a number of was:
..* Training for such a high dimensional input/output environment made training very slow. The solution had to focus on trying to improve training time. 
..* Finding the right hyperparameters via tunning. 
..* For action values that is continuous, dealing with noise correctly allows for more generalization and makes the agent convergence more effective.
* Using a DDPG  where the actor (policy-based) critic (values based), are combined to use the most effective parts of each algorithm. 
..* The actor based method has high variance but is more generalizable 
..* The values-based method has lower variance but higher bias.
..* The policy-based method required a lot of data samples and training can be slow. it has to wait until the end of the episode to update the policy.
..* The critic used temporal difference learning and updates the function after each step. The approximates a value function used to calculate the expected future reward. 
