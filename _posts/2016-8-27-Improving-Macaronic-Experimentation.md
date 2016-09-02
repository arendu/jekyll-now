---
layout: post
title: Refinements to macaronic user modeling
---
Things to consider regarding the testing of macaronic user model performance.

1. Randomly splitting test and train data. This feels wrong because there is an inherent assumption of _stationarity_. Users' learning on the other hand is constantly changing as the perform more hits. Consider a test example of a user doing their first sentence, while we have trained the model on several examples of the user doing tasks after a lot more experience. User x Experience adaptation might help, but would increase the number of features needed to be learned.

2. Improving speed of inference. Implement top _k_ using [matrix masking](http://docs.scipy.org/doc/numpy/reference/maskedarray.generic.html). Top _k_ would cause some issues. What if the messages from factors to a node do not overlap? The end result is a uniform message to the node. This seems bad, especially because the smaller _k_ gets the more likely this will happen. If only there was some method where a node accepts all incoming messages (which have been top _k_ truncated) and instead of just taking the product of the messages, it is aware of the truncation.

3. More to follow
