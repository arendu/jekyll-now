---
layout: post
title: Thoughts on using MTCS for macaronic learning
---

Monte Carlo Tree Search (MTCS) is a commonly used technique to solve/simplify the search problem that arises during game playing. An agent must consider multiple moves which can recursively lead to more moves to consider. This exponential tree search is not feasible in practice. In MTCS method can be divided into the following steps:

1. Selection: In this step we choose one of the many possible moves that are possible from the current state of the game. A simple selection procedure is to randomly select the move, a better alternative is to treat the selection process as a _multi-armed bandit_ problem and select the next move using the [_UCB1_ algorithm](https://www.cs.bham.ac.uk/internal/courses/robotics/lectures/ucb1.pdf). Note: UCB1's multi-armed bandit assumption implies that with each move there is some immediate reward that can be measured. It is not clear how this might work in real game playing scenarios, where the reward only shows up at the end of the game.

2. Expansion: Once selection is completed (We have glossed over stopping conditions for algorithms like UCB1), we pick a move. From this move, 'expand' to one or more 'next moves'. Essentially, if we are at a node $$R$$ and the selection step brings us to node $$L$$, we expand the children of $$L$$. Once we have the possible children of $$L$$ we pick one of them $$C$$.

3. Simulation: Once we have $$C$$ we run simulations of the game until the end of the game. For each simulation we track the number of wins and losses.

4. Backpropagation
 
Things to consider regarding the testing of macaronic user model performance.

1. Randomly splitting test and train data. This feels wrong because there is an inherent assumption of _stationarity_. Users' learning on the other hand is constantly changing as the perform more hits. Consider a test example of a user doing their first sentence, while we have trained the model on several examples of the user doing tasks after a lot more experience. User x Experience adaptation might help, but would increase the number of features needed to be learned.

2. Improving speed of inference. Implement top _k_ using [matrix masking](http://docs.scipy.org/doc/numpy/reference/maskedarray.generic.html). Top _k_ would cause some issues. What if the messages from factors to a node do not overlap? The end result is a uniform message to the node. This seems bad, especially because the smaller _k_ gets the more likely this will happen. If only there was some method where a node accepts all incoming messages (which have been top _k_ truncated) and instead of just taking the product of the messages, it is aware of the truncation.

3. More to follow
