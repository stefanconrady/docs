# Game 3

> "In Games 1 and 2 you didn’t have to do anything, but this time you do. There is one back-door path from X to Y, X←B→Y, which can only be blocked by controlling for B. If B is unobservable, then there is no way of estimating the effect of X on Y without running a randomized controlled experiment. Some (in fact, most) statisticians in this situation would control for A, as a proxy for the unobservable variable B, but this only partially eliminates the confounding bias and introduces a new collider bias." (Pearl, p. 160)

### Game 3 in BayesiaLab

As with the earlier games, we encode Game 3 as a causal Bayesian network graph:

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_BackDoor3.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692042150/BoW\_BackDoor3\_zmo3jq.xbl)

* Again, the probabilities are fictitious and irrelevant.
* We select `Main Menu > Analysis > Visual > Graph > Influence Paths to Target` to analyze the paths from X to Y.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692042253/BackDoorCriterionGame3a_l5efzh.mp4" %}

* Given the presence of a noncausal path (highlighted in pink), it becomes clear that we need to control for B to block that path.
* Here, "fixing the probabilities" of B are a practical way of controlling for that variable. Note that the states and the values of the variable are irrelevant.&#x20;

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692042253/BackDoorCriterionGame3b_m7strx.mp4" %}

* Now, after controlling for B, only one causal path remains, highlighted in blue, which allows us to estimate the effect of X and Y.
* However, if B were unobservable ("not observable" or "hidden" in BayesiaLab terminology), some statisticians would perhaps propose to control for A as a proxy of B.&#x20;
* Let's try that scenario as well. We are now fixing A while leaving B "open."

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692042253/BackDoorCriterionGame3c_o5heib.mp4" %}

* The Influence Path Analysis reveals that controlling for proxy A does not achieve our objective.
* Not only does it not block the noncausal path X←B→Y, controlling for A introduces an additional noncausal path X→A ←B→Y, i.e., another bias that prevents us from estimating the effect of X on Y.
* This phenomenon is known as "collider bias," as it is produced by conditioning on a collider, such as A.
