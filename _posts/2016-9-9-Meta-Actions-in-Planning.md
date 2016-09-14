---
layout: post
title: Meta Actions in MDPs
---
Often in planning the lowest level of actions are defined and we hope the learning algorithm will eventually learn to compose these low level actions in sensible ways. One way to speed up convergence of the various iteration algorithms (value iteration, policy iteration etc) is to define not just low level actions, but pre-set sequences of actions as well. Instead of only sampling low-level actions the algorithm can also pick a meta action, which then executes an entire sequence. We could also learn these meta actions automatically as [this](http://www.cs.mcgill.ca/~pcastr/cpewrl11.pdf) paper describes.

Example from [this](https://www.youtube.com/watch?v=yS5F_vm9Ahk) is of building stairs or single column towers in minecraft, eventually we might learn that building stairs/towers involves the repeated execution of blocks on top of eachother. But if these actions were encoded as one meta action if will speed up convergence.

This is also called temporarily extended actions. This idea is also cast as a sub-goal planning. Instead of pre-difining sequence of actions, we plan in a higher level space i.e. make high level decisions before dealing with the details of low level actions.
