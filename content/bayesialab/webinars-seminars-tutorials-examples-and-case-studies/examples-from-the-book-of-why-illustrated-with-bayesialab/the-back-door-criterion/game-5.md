# Game 5

> "Game 5 is just Game 4 with a little extra wrinkle. Now a second back-door path X←B←C→Y needs to be closed. If we close this path by controlling for B, then we open up the M-shaped path X←A→B←C→Y. To close that path, we must control for A or C as well. However, notice that we could just control for C alone; that would close the path X←B←C→Y and not affect the other path." (Pearl, p. 162)

### Game 5 in BayesiaLab

Here we have the causal Bayesian network corresponding to Game 5:​

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_BackDoor5.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692042979/BoW\_BackDoor5\_uzpibf.xbl)

* Select `Main Menu > Analysis > Visual > Graph > Influence Paths to Target` and see that there is a noncausal path that needs to be blocked.
* You can block this path by fixing the probability distribution of variable C.
* You can check if this proposed approach is correct by setting your evidence — Fix Probabilities on C — and then running the Influence Paths Analysis again.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692043044/BackDoorCriterionGame5_fafdzr.mp4" %}

&#x20;
