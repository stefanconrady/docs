# Game 4

"This one introduces a new kind of bias, called 'M-bias' (named for the shape of the graph). \[...]

M-bias puts a finger on what is wrong with the traditional approach. It is incorrect to call a variable, like B, a confounder merely because it is associated with both X and Y. To reiterate, X and Y are unconfounded if we do not control for B. B only becomes a confounder when you control for it!" (Pearl, pp. 161–162)

### Game 4 in BayesiaLab

The structure of this example seems simple and can be easily analyzed in BayesiaLab:​

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_BackDoor4.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692042794/BoW\_BackDoor4\_gmqv2p.xbl)

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692042863/BackDoorCriterionGame4a_dobmlq.mp4" %}

* Given that B is a collider, there is no open path and, thus, there is no effect of X on Y at all.&#x20;
* As a result, nothing needs to be blocked.
* However, as Pearl explains, if one were to apply a traditional three-step for a confounder, one might (incorrectly) conclude that B should be controlled for as a confounder.
* Let's try this scenario in BayesiaLab and see what happens.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692042864/BackDoorCriterionGame4b_b8m1da.mp4" %}

* By controlling for B, we inadvertently open up a noncausal path between X and Y, i.e., we are introducing a bias.
* The Influence Path Analysis highlights the M-shape, for which this bias is known.
