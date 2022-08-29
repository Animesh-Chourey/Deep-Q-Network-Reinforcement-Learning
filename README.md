# Atari Breakout using Reinforcement Learning

A Deep Q-network is trained to play the game Atari Breakout. [OpenAI baselines](https://github.com/openai/baselines) is used. The environment for Atari Breakout is created using OpenAI Gym.

Here, some improvements have been made to the baseline implementation:
* Adam optimiser has been substituted with RMSprop.
* Learning rate is set to  0.0001 with discount factor (rho) set to 0.99.
* To manage the memory issue, size of replay buffer is reduced to 10000 from 100000.
* The batch is drawn and and every four frames the network is updated only after replay buffer is full (in baseline implementation batch is drawn and updated only after the replay buffer size is larger than the batch size).
* Instead of storing the return of the last 100 episodes, the return of every episode is stored.

### Testing
The trained model with the conditions mentioned before is loaded for testing. The Atari Breakout environment is created by employing the same wrapper used for training the model. Ten episodes are recorded using the greedy policy based on the trained Deep Q-Network