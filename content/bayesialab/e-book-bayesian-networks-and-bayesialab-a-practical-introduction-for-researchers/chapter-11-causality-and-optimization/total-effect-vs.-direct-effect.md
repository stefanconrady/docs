# Total Effect vs. Direct Effect

### Simpson's Paradox Revisited

Why are we using the term “Direct Effect” instead of “causal effect,” which is obviously what we are looking for? It helps to recall the Simpson’s Paradox example from the previous chapter. Through path analysis, we were able to distinguish between causal (blue ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096153/Blue-Causal-Arc\_hqudas.svg)) and non-causal paths (pink ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096326/Pink-Non-Causal-Arc\_nzhjm9.svg)).&#x20;

We argued that the arc $$X → Y$$, i.e., the direct causal path, represents the causal effect. By adjusting for $$Z$$ and thus blocking the non-causal path $$X ← Z → Y$$, we were able to isolate the “direct effect” of $$X$$ on $$Y$$.&#x20;

However, if had we not adjusted for $$Z$$, both the causal and the non-causal path would remain open, and we would obtain the “total effect.” This is indeed the nomenclature we follow in BayesiaLab.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/webinars-seminars-examples/Simpsons-Paradox/Simpson.svg)

By invoking Direct Effect, BayesiaLab will automatically perform Likelihood Matching on all Confounders and estimate the causal effect.&#x20;

### **Direct Effect**

To emphasize the distinction between Direct Effect and Total Effect, we look one more time at Simpson’s Paradox ([SimpsonsParadox.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1691095434/SimpsonsParadox\_sg7fnv.xbl)).

* Click X and then select `Main Menu > Analysis > Report > Target Analysis > Direct Effects on Target`.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083801/DirectEffectsOnTarget_c01dzd.mp4" %}

We immediately obtain a report that shows a Direct Effect of −0.1. This value is identical to the Average Treatment Effect we computed in the previous chapter. As expected, adjustment by stratification, Graph Surgery, and Likelihood Matching provides the same effect estimate.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096866/SimpsonDirectEffectOnTarget_rj5z8z.png" alt="" width="563"><figcaption></figcaption></figure>

### Total Effect

For comparison, we now estimate the Total Effect:

* Select `Main Menu > Analysis > Report > Target Analysis > Total Effects on Target`.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083803/TotalEffectsOnTarget_nptol9.mp4" %}

The resulting report window now shows the Total Effect, which amounts to +0.1.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691097151/SimpsonTotalEffectsOnTarget_bgpnmo.png" alt="" width="563"><figcaption></figcaption></figure>

This result matches the naive estimator, i.e., the effect we observe when considering the whole population, which is clearly not the causal effect. So, why would we need to estimate the Total Effect at all? It would be the only correct estimator for performing observational inference, i.e., prediction. If we were merely observing treated versus not treated patients instead of performing an intervention, the Total Effect provides the expected change of the outcome variable.

#### &#x20;<a href="#h3__1075508365" id="h3__1075508365"></a>
