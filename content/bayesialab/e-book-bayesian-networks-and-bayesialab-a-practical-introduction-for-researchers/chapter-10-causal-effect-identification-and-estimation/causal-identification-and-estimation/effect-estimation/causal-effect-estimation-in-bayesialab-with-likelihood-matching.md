# Causal Effect Estimation in BayesiaLab with Likelihood Matching

We now introduce Causal Effect Estimation by means of Likelihood Matching. Given the simplicity of Simpson’s Paradox example, the need for yet another estimation method may not be immediately apparent. The advantages of Likelihood Matching will only become clear as we study a more complex domain, such as the marketing mix example of the next chapter. However, the current example makes it easy to explain Likelihood Matching.

### **Intuition for Matching**

In statistics, matching refers to the technique that makes confounder distributions of the treated and untreated sub-populations as similar as possible to each other. As such, applying matching to variables qualifies as adjustment, and we can use it with the objective of keeping causal paths open and blocking non-causal paths. In the Simpson’s Paradox example, matching is fairly simple as we only need to match a single binary variable, i.e., _Gender_. That will meet our requirement for adjustment and block the only non-causal path in our model.

As our terminology of “blocking paths by matching” may not be understood outside the world of graphical models and Bayesian networks, we can offer a more intuitive interpretation of matching, which our example can illustrate very well.

Because of the self-selection phenomenon of our population, Gender distribution is a function of Treatment. In other words, of those who are treated, 75% turn out to be male. Among untreated patients, only 25% are male.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/Matching1.svg)![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/Matching2.svg)

Given that we know that Gender has a causal effect on Outcome (men are more likely to recover than women, with or without treatment), and given this difference in gender composition, comparing the outcomes between the treated and non-treated patients is clearly not an apples-to-apples comparison.

We can propose a common-sense solution to this predicament. How about searching for a subset of patients within treated and non-treated groups, which have an identical gender mix, as illustrated below?

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/webinars-seminars-examples/Simpsons-Paradox/Matching2.svg" alt="" width="563"><figcaption></figcaption></figure>

In statistical matching, this process typically involves the selection of units in such a way that comparable groups are created:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/webinars-seminars-examples/Simpsons-Paradox/Matching3.svg" alt=""><figcaption></figcaption></figure>

In practice, this can be more challenging as the observed units typically have more than just a single binary attribute. So, the idea of matching has to be extended to higher dimensions, and the observed units need to be matched on a range of attributes, including both continuous and discrete variables.

However, matching observations exactly with regard to all covariates is rarely feasible. For instance, patients are characterized by dozens or even hundreds of attributes and comorbidities. Finding two matching patients would be difficult enough, but finding populations with many matching pairs of patients would presumably be impossible.

So, how does randomization do it? Actually, randomization does not guarantee identical populations but rather ensures that the distributions of confounders are balanced between the populations under study. So, to pursue balanced confounders instead of pursuing perfect matches, numerous similarity measures have been proposed for matching.

The concept of Propensity Score Matching has become a particularly popular method ([Rubin and Rosenbaum, 1983](https://academic.oup.com/biomet/article/70/1/41/240879)). Instead of matching individuals on their high-dimensional attributes, we would match observations by their probability of treatment, i.e., P(X=1|Z), which is known as the Propensity Score. Rubin and Rosenbaum have shown that matching on the propensity score achieves a balance of the covariate distributions.

However, matching on the Propensity Score requires the score itself to be estimated first. Conventional models only represent the outcome variable as a function of the treatment variable and the confounders, i.e., P(Y|X, Z). If we need to understand the relationship between the treatment and the confounders, i.e., P(X|Z), we have to estimate this separately. This usually means fitting a function, such as a regression, that models the propensity score, PS=P(X|Z). For binary treatment variables, logistic regression is a common choice for the functional form.

### **Likelihood Matching**

With BayesiaLab's Likelihood Matching, we do not directly match the underlying observations. Rather we match the distributions of the relevant nodes on the basis of the joint probability distribution represented by the Bayesian network. In our example, we need to ensure that the gender compositions of untreated and treated groups are the same, i.e., a 50/50 gender mix. This _theoretically ideal_ condition is shown in the Monitors below.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/Matching3.svg) ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/Matching4.svg)

However, the actual distributions reveal the inequality of gender distributions for the untreated and the treated.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/Matching1.svg) ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/Matching2.svg)

How can we overcome this? By simply using Probabilistic Evidence to set a 50/50 gender mix, i.e., the marginal distribution of Gender, upon setting evidence on Treatment. We can also right-click on the Monitor for _Gender_ and select Fix Probabilities from the Contextual Menu. This will automatically use Probabilistic Evidence to set the current marginal distribution after each conditioning on Treatment, or any other node.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/FixProbabilities.png" alt=""><figcaption></figcaption></figure>

With Fix Probabilities applied, the distribution of Gender in its Monitor is highlighted in purple.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/FixProbabilities2.png" alt=""><figcaption></figcaption></figure>

Other than colors, nothing appears to have changed. However, once we set the values Treatment=False and Treatment=True, we see that the distribution for Gender does not change. We can also observe that the corresponding posterior probabilities for _Outcome_ are the same as those obtained with Graph Surgery.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/FixProbabilities3.svg)![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/FixProbabilities4.svg)

With that, we can once again calculate the Average Causal Effect:

$$ACE = P\left( {Y = 1|do(X = 1)} \right) - P\left( {Y = 1|do(X = 0)} \right) = - 0.1$$

For now, Likelihood Matching applied to Simpson's Paradox may not seem like a breakthrough method. Conceptually and practically, it appears to be another form of adjustment. The fundamental advantages of Likelihood Matching will become clear in the context of the next chapter, [Causality and Optimization](../../../chapter-11-causality-and-optimization/).
