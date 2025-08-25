# reinforcement-learning-chess-agent
Making a chess agent using Reinforcement Learning, Sparse Q, and Deep Q  

  
Project requires chess, numpy, and torch  
You must also acquire the latest version of stockfish and place it in the same directory as the project for scoring to function properly. https://github.com/official-stockfish/Stockfish  
  
  
Chess is a great example of a strategic game where both players have perfect information. This makes it almost entirely skill based with very little luck involved. Chess is also a very complex game. With an estimated 10^45 possible board states, memorizing the best move in every scenario is impossible, meaning players have to rely on intuition after their opening moves. This makes it an ideal candidate to train an artificial intelligence model on, and be able to reliably gauge it's performance.  


# Methodologies:  
  
## Reinforcement Learning (RL)  
Reinforcement learning is an area of machine learning where agents learn to make good decisions based on rewards given for past actions in an environment. These rewards provide the agent feedback allowing it to update its behavior to maximize cumulative rewards over time. Rewards can also be weighted to drive the agent towards more important goals such as checkmate rather than piece capture. RL is well-suited for problems like chess because of its focus on sequential decision-making and long-term strategy.  
  
## Q-learning  
Q-learning is a value-based RL algorithm where the agent learns a Q-function, which estimates the expected cumulative reward of taking a certain action in a given state. However, learning the Q function in chess can take an extreme amount of training due to the impossibly large number of board states and possible actions in chess.  
  
## Sparse Q learning  
Sparse Q-learning is a modification of standard Q-learning that focuses on efficiently handling large or continuous state spaces by only storing and updating a sparse subset of Q-values. In our case this is only Q values that have been explored. This makes it so the learning and memory required to map the vast state and action space associated with chess (and even minichess) is much reduced. This will allow our rather limited resources to be able to learn as much of the Q table as possible.  
  
## Deep Q learning  
Deep Q-learning extends Q-learning by using a deep neural network to approximate the Q-function, instead of using a lookup table. This allows the agent to generalize across similar states and handle high-dimensional input spaces, like images and (in our case) chess boards.

Initially, we implemented a DQN to train a chess-playing agent on a standard 8x8 board. However, due to hardware limitations, the training process was infeasible. To address this, we simplified the problem to a smaller 5x3 “scarecrow” chess board, significantly reducing the state-action space while still retaining meaningful strategic elements of chess.
