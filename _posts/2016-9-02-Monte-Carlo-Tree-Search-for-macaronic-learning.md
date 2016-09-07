---
layout: post
title: Thoughts on using MTCS for macaronic learning
---

Monte Carlo Tree Search (MTCS) is a commonly used technique to solve/simplify the search problem that arises during game playing. An agent must consider multiple moves which can recursively lead to more moves to consider. This exponential tree search is not feasible in practice. Book-keeping in MTCS involves keeping track of wins and losses possible from each game state. In MTCS method can be divided into the following steps:

1. Selection: In this step we choose one of the many possible moves that are possible from the current state of the game. A simple selection procedure is to randomly select the move, a better alternative is to treat the selection process as a _multi-armed bandit_ problem and select the next move using the [_UCB1_ algorithm](https://www.cs.bham.ac.uk/internal/courses/robotics/lectures/ucb1.pdf). Note: UCB1's multi-armed bandit assumption implies that with each move there is some immediate reward that can be measured. It is not clear how this might work in real game playing scenarios, where the reward only shows up at the end of the game.

2. Expansion: Once selection is completed (We have glossed over stopping conditions for algorithms like UCB1), we pick a move. From this move, 'expand' to one or more 'next moves'. Essentially, if we are at a node $$R$$ and the selection step brings us to node $$L$$, we expand the children of $$L$$. Once we have the possible children of $$L$$ we pick one of them $$C$$.

3. Simulation: Once we have $$C$$ we run simulations of the game until the end of the game. For each simulation we track the number of wins and losses.

4. Backpropagation: The number of wins and losses are propagated back to the root node. By propagation we mean the wins and losses at each node are updated.


The issue in macaronic learning setting is that there is no way to run the simulation step. i.e. there is no objective win or loss that can be recorded by taking random steps.  
_to be continued_
 
