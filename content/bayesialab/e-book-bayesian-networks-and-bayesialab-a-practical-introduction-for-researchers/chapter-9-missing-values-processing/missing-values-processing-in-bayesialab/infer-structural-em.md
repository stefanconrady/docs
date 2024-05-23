# Infer — Structural EM

Structural Expectation Maximization (or Structural EM for short) is the next available option under Infer. This method is very similar to [Dynamic Imputation](infer-dynamic-imputation.md), but instead of imputing values after each structural modification of the model, the set of observations is supplemented with one weighted observation per combination of the states of the jointly unobserved variables. Each weight equals the posterior joint probability of the corresponding state combination.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-20\_15-52-44.png)

Upon completion of the data import process, we perform structural learning again, analogously to what we did in the context of [Dynamic Imputation](infer-dynamic-imputation.md). As it turns out, the discovered structure is equivalent to the one previously learned. Hence, we can immediately proceed to evaluate the performance.

The distributions produced by Structural EM are quite similar to those obtained with [Dynamic Imputation](infer-dynamic-imputation.md). At least, in theory, Structural EM should perform slightly better. However, the computational cost can be even higher than that of [Dynamic Imputation](infer-dynamic-imputation.md) because the computational cost of Structural EM also depends on the number of state combinations of the jointly unobserved variables.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690999946/MissingValuesProcessingStructuralEM_e6qszs.svg" alt="" width="563"><figcaption></figcaption></figure>
