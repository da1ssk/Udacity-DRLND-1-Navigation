# Udacity Deep Reinforcement Learning Nanodegree Project #1: Navigation
In this project, we train an agent to navigate and collect bananas in a 3D square space.

The simulation environment is based on Unity Environment. The code is available [here](https://github.com/udacity/deep-reinforcement-learning/tree/master/python/unityagents)

![banana](https://user-images.githubusercontent.com/1985201/113376563-040bbc00-9340-11eb-9bdd-3e5df2ec9e9f.gif)

### Rewards
- +1 for getting a yellow banana
- -1 for getting a blue banana

### States
There are 37 states in this environment. Those include the agent's velocity and ray-based perception of objects around the agent's forward direction.

However, there is no clear description of each state element from Udacity as discussed [here](https://knowledge.udacity.com/questions/22697)

### Actions
The agent can take 4 discrete actions.

0. Move forward
1. Move backward.
2. Turn left
3. Turn right.

### Criteria
If the average score of the latest 100 episodes exceeds +13, it is considered as solved.

## Getting started
Load `Navigation.ipynb` in Jupyter notebook, then follow the instruction.

You will need the `python` directory that is available [here](https://classroom.udacity.com/nanodegrees/nd893/parts/6b0c03a7-6667-4fcf-a9ed-dd41a2f76485/modules/e7499d4f-24f9-42ec-9864-23adcfa4e241/lessons/69bd42c6-b70e-4866-9764-9bfa8c03cdea/concepts/b6729be0-4a97-4c8d-b2c9-9eafe47939ac) in the Udacity workspace. Click the "Jupyter" logo to see the `python` directory.

## Report
The report can be found [here](Report.md)
