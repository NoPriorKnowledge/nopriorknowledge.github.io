---
layout: post
title: "Grokking: late learning of a generalisation mode"
date: 2026-04-07
abstract: "Literature survey"
---


Grokking (late generalization) is a phenomenon that has been first observed by Power et al. 2022 that can arrises during traing. Since then, various solutions to understand and control it has arrised (Liu et al., Nanda et al, Levi et al). NN learns the data representation through a hierarchical sequential representation of it. Could grokking be in fact the late learning of a generalisation mode ?  Through this paper, we take a mecanistic approach on this phenomenon through the weights dynamic itself to see if t* could be deductible from non linear second order statistic spectral values EDO ? Through this approach, can we induce / remove grokking via targeted spectral initialisation ? And can we persist this result in a non linear context ?

## stuff to do
- [ ] can we observe grokking on a simple 1hidden linear network on generated data ?
    - mod5 ADD ?


## sources

> [idea]
> Grokking [Power et al. 2022](https://arxiv.org/abs/2201.02177) asses that a network Will first mémorise data then généralise it later (training loss : 0->high->abrupt fall). Could grokking be in fact the late learning of a généralisation mode which was masked by memorieation ? We can take an analytic approach on this. Maybe it’s just a weak singular value that is then learned at the very end. Can we induce grokking by changing spectral data or the init of the weights ?

___
[OMNIGROK: GROKKING BEYOND ALGORITHMIC
DATA](https://arxiv.org/pdf/2210.01117)
*Liu, Michaud and Tegmark*
>Induced grokking and 'LU mechanism'.

___

[GROKKING AS THE TRANSITION FROM LAZY TO RICH
TRAINING DYNAMICS](https://arxiv.org/pdf/2310.06110)
*Kumar, et al. 2024*
>Grokking arises when the initial neural tangent kernel and y are not aligned.

 If we zoom in on just modular arithmetic tasks, or more broadly "algorithmic" style datasets, which were originally used to show this phenomenon in transformers by Power et al. (https://arxiv.org/pdf/2201.02177):

Then MLPs can exhibit grokking on the same task: e.g. https://arxiv.org/pdf/2301.02679 where you concatenate the one-hot encodings of the digits and use a two layer MLP with quadratic activations (I have also replicated this with relu activations and found that it exhibits grokking, though the behavior is more sharp and clear with quadratic)

I'm biased on this one, but we also wrote a paper on grokking where we showed that even kernels can exhibit grokking when they have a feature learning mechanism, and in this way we found that you don't even need neural networks or gradient descent optimization methods to replicate the delayed generalization type curves you see in grokking! Which I found surprising and in our discussion we expand a bit on why we feel this result was important in the broader ML context. Our paper is: https://arxiv.org/pdf/2407.20199

There are other references of interest that you may like in the area of grokking with simpler architectures or non-neural models, for example:

https://arxiv.org/pdf/2310.06110

https://arxiv.org/pdf/2310.17247
