# Navigation project report

## Learning Algorithm

I chose to use the DQN code that I used for the exercises to train the agent for this project.

The training algorithm thus is the Deep Q-Learning with experience replay and fixed Q-targets.

The hyperparameters that are passed to `dqn` function is modified so it will match the environment.

- `n_episodes = 1800`  # max number of episodes
- `max_t = 300`  # max time steps per episode
- `eps_start = 1.0`  # starting value of epsilon-greedy action selection
- `eps_end = 0.01`  # minimum value of epsilon
- `eps_decay = 0.995`  # multiplicative factor per every episode for decreasing epsilon

### Agent ([`dqn_agent.py`](dqn_agent.py))
I use the `Agent` class from the exercises as is.

Here are the hyperparameters.
- `BUFFER_SIZE = int(1e5)`  # replay buffer size
- `BATCH_SIZE = 64`         # minibatch size
- `GAMMA = 0.99`            # discount factor
- `TAU = 1e-3`              # for soft update of target parameters
- `LR = 5e-4`               # learning rate 
- `UPDATE_EVERY = 4`        # how often to update the network

### Model architecture ([`model.py`](model.py))
I use the `QNetwork` class from the exercises as is, too.

It is a neural network with fully-connected layers. First and second hidden layer is followed by a rectifier nonlinearity (that is, `max(0,x)`).

- Input: 37 nodes corresponding to each state element
- First layer: 64 nodes
- Second layer: 64 nodes
- Output: 4 nodes corresponding to the value of each action

## Plot of Rewards
Here is the average score for every 100 episodes.

```
Episode 100	Average Score: 1.28
Episode 200	Average Score: 4.41
Episode 300	Average Score: 8.39
Episode 400	Average Score: 10.43
Episode 500	Average Score: 12.72
Episode 517	Average Score: 13.05
Environment solved in 417 episodes!	 Average Score: 13.05
```

Here is the plot of rewards over episodes.

![rewards](https://user-images.githubusercontent.com/1985201/113491173-c8d2cf80-949c-11eb-8524-798cc024afc7.png)

## Ideas for Future Work

### State from pixels
As suggested [here](https://github.com/udacity/deep-reinforcement-learning/blob/master/p1_navigation/README.md), it would be interesting to learn directly from pixels. This would be a good exercise to familiarize myself to handle image input and apply the techniques to other problems such as playing video games which is super exciting.

### Tuning Hyperparameters
Since I know the hyperparameters work well for the lunarlandar-v2 exercise, it is natural to think that it can be used for this project. It will be insightful to see which parameters affect what aspects of learning.

### Applying advanced improvements
Obvious future work is to apply more advanced techniques introduced in the course: DDQN, Prioritized Experience Replay, Dueling DQN, and Rainbow. I’m curious to know how much of improvement I can expect for this particular problem. I tend to think the cost-effectiveness first when I implement something, thus the next step is to read and evaluate these scientific papers.

### Visualization
Visualizing how the trained agent is another obvious step. To see training episodes as well as the fully trained agent will be useful to get even more insights for the training architectures and hyperparameters.

### Development cycle
I find it frustrated sometimes by not knowing what Jupyter notebook is doing when it executes time-consuming process. I often had to refresh the workspace to escape from those unknown states. To efficiently run the development cycle, it is best to setup a local environment that is not dependent on Jupyter notebook.
