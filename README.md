# DQN implemented in PyTorch to play CartPole Game

### Basic intuition
The agent has to decide between two actions - moving the cart left or right - so that the pole attached to it stays upright. As the agent observes the current state of the environment and chooses
an action, the environment *transitions* to a new state, and also
returns a reward that indicates the consequences of the action. In this task, rewards are +1 for every incremental timestep and the environment terminates if the pole falls over too far or the cart moves more then 2.4 units away from center.

### DQN
Our environment is deterministic, so all equations presented here are also formulated deterministically for the sake of simplicity. In the reinforcement learning literature, they would also contain expectations over stochastic transitions in the environment.

The main idea behind Q-learning is that if we had a function
:math:`Q^*: State \times Action \rightarrow \mathbb{R}`, that could tell us what our return would be, if we were to take an action in a given state, then we could easily construct a policy that maximizes our rewards:

.. math:: \pi^*(s) = \arg\!\max_a \ Q^*(s, a)

However, we don't know everything about the world, so we don't have access to :math:`Q^*`. But, since neural networks are universal function approximators, we can simply create one and train it to resemble :math:`Q^*`.

To minimise the error, we will use [Huber Loss](https://en.wikipedia.org/wiki/Huber_loss)

Input of the model is difference between the current state and previous state patches, and it has two output which is going to left or right in order to stay in the game longer

### Output


### How to Use:
1. Install pytorch version 1.4.0 above
2. Clone this repo
3. Run `dqn.py`
**Change the hyperparameters if you want to experiment with the output**

## Contributor
<a href="https://github.com/fadilparves/dqn-pytorch-cartpole/graphs/contributors">
  <img src="https://contributors-img.web.app/image?repo=fadilparves/dqn-pytorch-cartpole" />
</a>