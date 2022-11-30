# Value Based Methods Navigation Project Report

This project builds on the Deep Q-Network solution provided as part of Udacity's 'Value-based-methods-main' Github repo
* [Deep Q-Network](https://github.com/udacity/Value-based-methods/tree/main/dqn)

While this solution interacted with an OpenAI Gym environment, this project replaced that environment with Unity's Bananna Collector environment.

# Learning Algorithm

A Pytorch Deep Q-Network (DQN) using replay memory was trained to solve the environment.

In PyTorch, the neural network layers are defined in the init function and the forward pass is defined in the forward function, which is invoked automatically when the class is called.

3 Linear layers were used with a Relu activation function.  The first layer takes the input state_size (37) and is fully connected to 64 nodes.  The second layer takes those 64 nodes and is fully connected to another 64 nodes.  The third layer takes 64 nodes and is fully connected to the output action_size (4).

An agent is defined that interacts with the environment and updates the DQN.

An epsilon value of 1.0 with a decay rate of 0.005 was used.  A random draw again epsilon was used to balance exploration vs. exploitation when selecting action values.  A discount factor of 0.99 was used and a learning rate of 5e-4 was used.  

Every 4 time steps, the network will sample actions from replay memory as long as the size of the memory has reached 32 samples. These samples will be used to update the network (weights from local copied to target) for use when the agent needs to take the next action.

# Plot of Rewards

![Scores Plot](https://github.com/mindcriminal/Udacity_RL_Nanodegree_Projects/blob/main/Value_Based_Methods_Navigation/Scores_Per_Episode.png)

The environment is considered solved when the average reward for an episode reaches 13.00.  My environment was solved in 516 episodes with an Average Score value of 13.03.  Max scores per episode were considerbly higher.

# Ideas For Future Work

Several improvements to a standard DQN with Replay Memory have been suggested in the coursework, namely Double DQNs, Dueling DQNs and replacing Replay Memory with Prioritized Replay Memory.  A hyperparameter sweep could also be used to improve the standard DQN as well.

It is also important to understand the definition of done for this environment that is not specified anywhere.  I could not find any information on when/why the done flag gets set in the environment.  This information might help with hyperparameter selection in the future.
