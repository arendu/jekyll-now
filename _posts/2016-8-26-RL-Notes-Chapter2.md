---
layout: post
title: RL Notes Chapter 2
---
### N-Armed Bandits
Definitions:

1. _Value_ of an _action_ is the mean expected reward obtained by performing that action.

Some useful distinctions I found:
[Difference between n-armed-bandit testing and A/B testing](http://conversionxl.com/bandit-tests/)

2. Action-Value Methods: The value of taking the action $a$ at time $t$ is given by: 
\begin{align} 
Q_t(a) = \frac{r_1 + r_2 + \ldots + r_k}{k}
\end{align} 
Here $k$ is the number of times action $a$ has already been selected i.e. in previous plays. This is known as _sample-average_ method of estimating the value of an action.

3. Selecting the best action using _sample-average_ method is a perfectly reasonable. This is called _greedy_ section.

4. A tweak on _greedy_ selection is to select a non-best action in some small (\epsilon) portion of plays. This is called _$\epsilon$-greedy_.

5. The logical extension is obviously selecting the action using the values of all the actions $\script{A}$ at time $t$ and applying a _softmax_ over these values. This will result is a nice distribution over the actions. It's now perfectly reasonable to select or sample an action from this distribution. This is known as _softmax-action selction_.
\begin{align}
P(a) &= \frac{\exp^{Q_t(a)/\tau}{\sum_b \exp^{Q_t(b)/\tau}} 
\end{align}
Here $\tau$ is a hyperparameter called the _temperature_. As $\tau$ is increased the selection is more uniform and as tau is reduced the selection is more greedy.

6. The averaging based methods of selection assume _stationarity_. If we want to constantly _track_ changing values section 2.5 details how averaging is essentially an incremental update with changing (reducing) step sizes. If the step size is kept constant (or changed by some other heuristic) we no longer implicitly assume stationarity.



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