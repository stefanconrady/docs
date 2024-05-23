# Smoking and Asthma

### Context&#x20;

Judea Pearl concludes Chapter 4 in [The Book of Why](https://amzn.to/3igHXm5) with a model from a paper by [Andrew Forbes and Elizabeth Williamson](https://onlinelibrary.wiley.com/doi/full/10.1111/resp.12238) on the effect of smoking (X) on adult asthma (Y). It is the final example illustrating the [Back-Door Criterion](the-back-door-criterion/). (Pearl, p. 164)

Here is the causal Bayesian network for this problem domain:​

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_Asthma.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692043185/BoW\_Asthma\_xutg42.xbl)

* You can use `Main Menu > Analysis > Visual > Graph > Influence Paths to Target` to find all paths from Smoking to Asthma.
* As it turns out, there are 14 noncausal paths and one causal path!
* Our task is to block all 14 noncausal paths and keep the one causal path open. If we can't do that, we won't be able to estimate the effect causal effect of Smoking on Asthma.
* In this example, the variable Predisposition toward Asthma provides an extra challenge. It is a not-observable (or hidden) variable. Hence, you cannot adjust for it, which means you cannot use it to block any of the 14 noncausal paths.
* In the end, you have to adjust for five variables (highlighted in green in the screen capture) to block all noncausal paths to estimate the causal effect of Smoking on Asthma.
* After controlling for these variables, only one causal path remains, representing the relationship of interest, i.e., the effect of Smoking on Asthma.

### Workflow Animation

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692049771/SmokingAsthma_py5ay8.mp4" %}
