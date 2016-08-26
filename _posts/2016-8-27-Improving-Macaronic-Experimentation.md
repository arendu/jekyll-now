---
layout: post
title: RL Notes Chapter 2
---
Things to consider regarding the testing of macaronic user model performance.
1. Randomly splitting test and train data. This feels wrong because there is an inherent assumption of _stationarity_. Users' learning on the other hand is constantly changing as the perform more hits. Consider a test example of a user doing their first sentence, while we have trained the model on several examples of the user doing tasks after a lot more experience. User x Experience adaptation might help, but would increase the number of features needed to be learned.

this is a test
here are some latex equations.
$$ a = b + c + \frac{1}{2}$$

some more eq
\begin{align}
k  &= 2 \times \delta \\\\
&= a + \mathbf{c}
\end{align}

some more eq with align inside double dollar:

$$ \begin{align}
k  &= 2 \times \delta \\
&= a + \mathbf{c}
\end{align} $$
