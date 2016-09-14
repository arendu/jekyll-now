---
layout: post
title: Parameters, Estimators and Estimates
---

The causal inference class today covered some very basic ideas that I frequently have problems with. I 'know' what estimates and estimators are but could not clearly explain them to a lay person (which probably reflects some holes in my knowledge). Today's class cleared some basic ideas.

1. A distribution $$p(x_1, x_2, \ldots, x_k)$$ captures some properties of the world.

2. We might be interested in specific properties within this distribution, say $$E[X_1]$$ or $$p(X_2 = x)$$ etc. These are _fixed_ but _unknown_ properties.

3. These properties of interest either _parameters_ of our distribution e.g. $$p(X_2 = x)$$ which are also known as _estimands_.

4. Typically there are too many parameters to measure. So we need to come up with functions or algorithms that will give us an approximate value of the parameters we are interested in. These functions are _estimators_.

5. The input for an estimator is some _subset_ of the distribution, i.e. we have to  get a representative sample $$\mathbf{X}$$ from  the distribution $$p(x_1, x_2, \ldots, x_k)$$ which will serve as the input for our estimator function. $$\mathbf{X}$$ is a matrix of dimensionality $$(N x k)$$ where $$N$$ is the number of samples drawn and $$k$$ is the number of variables in one sample.

6. Now an estimand, say $$\Theta = E[x_1]$$ can be approximately computed or estimated  using the estimator $$\hat{\Theta}(\mathbf{X}) = 1/N \sum_{i=1}^N x_1^i$$. Note: the input to $$\hat{\Theta}$$ is $$\mathbf{X}$$ which is a random sample and therefor the estimate is also a random variable. Note: This estimator is making assumptions about how the samples were generated, specifically it assumes the samples are iid.

7. A good estimator has no bias $$\Theta - E[\hat{\Theta}(\mathbf{X})] = 0$$ and low variance $$Var(\hat{\Theta}(\mathbf{X})) = E[\hat{\Theta}(\mathbf{X}) - E[\hat{\Theta}(\mathbf{X})]^2].  Note: that the true value of $$\Theta$$ does not show up in the variance, it is just a measure of how different the output of the estimator is with different samples as input.

8. We can combine the properties of bias and variance into a single measure MSE, mean squared error $$MSE = E[(\Theta - \hat{\Theta}(\mathbf{X}))^2]$$. MSE can be decomposed as $$ bias^2 + variance$$. This can be seen using the identity $$E(X^2) = Var(X) + E(X)^2$$(??).

