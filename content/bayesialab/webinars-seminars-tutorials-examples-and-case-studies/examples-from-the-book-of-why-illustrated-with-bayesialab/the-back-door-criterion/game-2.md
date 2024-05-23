# Game 2

### Context

> "In this example you should think of A, B, C, and D as “pretreatment” variables. (The treatment, as usual, is X.) Now there is one back-door path X←A→ B←D→E→Y. This path is already blocked by the collider at B, so we don’t need to control for anything." (Pearl, p. 160)

### Game 2 in BayesiaLab&#x20;

For Game 2, we have once again created a causal Bayesian network, which is available for download here:​

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_BackDoor2.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692041222/BoW\_BackDoor2\_emvh8p.xbl)

* Note that the associated probability tables are fictitious. For our purposes, only the causal graph is relevant.
* As before, we select `Main Menu > Analysis > Visual > Graph > Influence Paths to Target` to analyze the paths from X to Y.​

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692041293/BackDoorCriterionGame2_zc9avo.mp4" %}

* We can see that there is no noncausal path.
* Hence, there is then no need to control for any variables.
