# TiC_TaC_ToE

Rules of the Game:
The game will be played on a 3x3 grid (9 cells) using numbers from 1 to 9. Each number can be used exactly once in the entire grid.

There are two players: one is the Reinforcement Learning (RL) agent and other is the environment.

The RL agent is given odd numbers {1, 3, 5, 7, 9} and the environment is given the even numbers {2, 4, 6, 8}

Each of them takes a turn. The player with odd numbers always goes first.

At each round, a player puts one unused number on a blank spot.

The objective is to make 15 points in a row, column or a diagonal. The player can use the opponent's numbers in the grid to make 15.

The game terminates when any one of the players makes 15.


The basic framework for this is:

Initialise the state

Define the action space for each state. (Be careful in defining actions. The actions are not the same for each state)

Define the winning states: the sum of three numbers in a row, column or diagonal is 15.

Define the terminal states (win,tie,loss)

Build the reward structure as below:

+10 if the agent wins (makes 15 points first)

-10 if the environment wins

0 if the game ends in a draw (no one is able to make 15 and the board is filled up)

-1 for each move agent takes

Define a step function which takes in an input of the agent’s action and state; and outputs the next state and reward. (Make sure you incorporate environment’s move in the next state).

For your reference: TCGame_Env.py file is provided with a basic structure of the code. The functions (and the comments) will provide an intuition of how the MDP would be formulated. Codes of a few functions are also provided to give you more sense on how to proceed with the MDP. Note: Using this framework is not compulsory, you can create your own framework and functions as well.

Build an agent that learns the game by Q-Learning. You can choose the hyperparameters (epsilon (decay rate), learning-rate, discount factor) of your choice. For that, you can train the model iteratively to obtain a good combination of hyperparameters. You won’t be evaluated on your choice of the hyperparameters. You need to submit only the final model. 

While updating the Q-values, if the next state is a terminal state, then the Q-values from that state are 0. (No action is possible from that state)

For a 64-bit system with 8GB RAM, it takes ~30 minutes to run 5Mn episodes.

Q-values convergence- check whether Q-values learnt by the agent have converged or not. Sample 4 state-action pairs and plot it with the number of episodes to understand the convergence.
