## DRL - DDPG Algorithm - Reacher Continuous Control
### Learning Algorithm
The Learning algorithm used in this project is a modification of the implementation used in the [pendulum environment](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum).

### Model Architecture
The Udacity provided DDPG code in PyTorch was used and adapted for this 20 agent environment.

The algorithm uses two deep neural networks (actor-critic) with the following struture:
- Actor    
    - Hidden: (input, 128)  - ReLU
    - Hidden: (128, 128)    - ReLU
    - Output: (128, 4)      - TanH

- Critic
    - Hidden: (input, 128)              - ReLU
    - Hidden: (128 + action_size, 128)  - ReLU
    - Output: (128, 1)                  - Linear


### Hyperparameters
- BUFFER_SIZE = int(1e6)  # replay buffer size
- BATCH_SIZE = 128        # minibatch size
- GAMMA = 0.99            # discount factor
- TAU = 1e-3              # for soft update of target parameters
- LR_ACTOR = 1e-4         # learning rate of the actor 
- LR_CRITIC = 1e-4        # learning rate of the critic
- WEIGHT_DECAY = 0.0 # L2 weight decay


## Results 

The figure below show the perfomance and results of my model. The model performs well. It was able to achieve the goal with 151 episodes.

![Udacity Results](https://github.com/nisheed75/Udacity-DRL-Continious-Control/blob/master/images/results.png)


## future improvements
1. Improve the DDPG alogorithm by applying Priority Experience Replay.
..1. Using this approach will:
...1. Reduce the training time
...1. Improve the stability of traning  
