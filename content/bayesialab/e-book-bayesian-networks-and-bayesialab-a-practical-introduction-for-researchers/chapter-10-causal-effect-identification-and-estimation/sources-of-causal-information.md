# Sources of Causal Information

### Causal Inference by Experiment <a href="#h3__1807606636" id="h3__1807606636"></a>

Randomized experiments have always been the gold standard for establishing causal effects. For instance, in the drug approval process, controlled experiments are mandatory. Without first having established and quantified the treatment effect, and any associated side effects, no new drug could win approval by the Federal Drug Administration.

### Causal Inference from Observational Data and Theory <a href="#h3_1933210033" id="h3_1933210033"></a>

However, in many other domains, experiments are not feasible, be it for ethical, economic, or practical reasons. For example, it is clear that a government could not create two different tax regimes to evaluate their respective impact on economic growth. Neither would it be possible to experiment with two different levels of carbon emissions to measure a warming effect on the global climate.

“So, what does our existing data say?” would be an obvious question from policymakers, especially given today’s high expectations concerning Big Data. Indeed, in lieu of experiments, we can attempt to find instances in which the proposed policy already applies (by some assignment mechanism) and compare those to other instances in which the policy does not apply.

However, as we will see in this chapter, performing causal inference on the basis of observational data requires an extensive range of assumptions, which can only come from theory, i.e., domain-specific knowledge. Despite all the wonderful advances in analytics in recent years, data alone, even Big Data, cannot prove the existence of causal effects.

### Historical Context <a href="#h2__65803433" id="h2__65803433"></a>

Today, we can openly discuss how to perform causal inference from observational data. For the better part of the 20th century, however, the prevailing opinion had been that speaking of causality without experiments is unscientific. Only towards the end of the century, this opposition had slowly eroded (Rubin 1974, Holland 1986), which subsequently led to numerous research efforts spanning philosophy, statistics, computer science, information theory, etc. The Potential Outcomes Framework has played an important role in this evolution of thought.

### Potential Outcomes Framework <a href="#h3_332620453" id="h3_332620453"></a>

Although there is no question about the common-sense meaning of “cause and effect,” for formal analysis, we require a precise mathematical definition. In the fields of social science and biostatistics, the potential outcomes framework is a widely accepted formalism for studying causal effects (the potential outcomes framework is also known as the counterfactual model, the Rubin model, or the Neyman-Rubin model). Rubin (1974) defines "causal effect" as follows:

> “Intuitively, the causal effect of one treatment, $$T=1$$, over another, $$T=0$$, for a particular unit and an interval of time from $$t_1$$ to $$t_2$$ is the difference between what would have happened at time $$t_2$$if the unit had been exposed to $$T=1$$ initiated at $$t_1$$ and what would have happened at $$t_2$$ if the unit had been exposed to $$T=0$$ initiated at $$t_1$$: ‘If an hour ago I had taken two aspirins instead of just a glass of water, my headache would now be gone,’ or because an hour ago I took two aspirins instead of just a glass of water, my headache is now gone.’ Our definition of the causal effect of $$T=1$$ versus $$T=0$$ treatment will reflect this intuitive meaning.”&#x20;

{% hint style="warning" %}
In this quote, we altered the original variable name $$E$$ to $$T=1$$ and $$C$$ to $$T=0$$ in order to be consistent with the nomenclature in the remainder of this chapter. $$T$$ is commonly used in the literature to denote the treatment condition.
{% endhint %}

* $$Y_{i,1}$$ Potential outcome of individual $$i$$ given treatment $$T=1$$ (e.g., taking two Aspirins)
* $$Y_{i,0}$$ Potential outcome of individual $$i$$ given treatment $$T=0$$ (e.g., drinking a glass of water)

The individual-level causal effect (ICE) is defined as the difference between the individual’s two potential outcomes, i.e.,

$$ICE = {Y_{i,1}} - {Y_{i,0}}$$

Given that we cannot rule out differences between individuals (effect heterogeneity), we define the average causal effect $$(ACE)$$ as the unweighted arithmetic mean of the individual-level causal effects:

$$ACE = E[{Y_{i,1}}] - E[{Y_{i,0}}]$$

$$E[⋅]$$ denotes the expected value, i.e., the unweighted arithmetic mean.

The challenge is that $$Y_{i,1}$$ (treatment) and $$Y_{i,0}$$ (non-treatment) can never be both observed for the same individual at the same time. We can only observe treatment or non-treatment, but not both.

So, where does this leave us? What we can produce easily is the “naive” estimator of association$$S$$ between the “treated” and the “untreated” sub-populations:

$$S = E[Y|T = 1] - E[Y|T = 0]$$

For notational convenience, we omit the index $$i$$ because we are now referring to sub-populations and not to an individual.

Because the sub-populations in the treated and untreated groups contain different individuals, $$S$$ is not necessarily a measure of causation, in contrast to$$ACE$$.

The question is, how can we move from what we can measure, i.e., the naive association, to the quantity of interest, i.e., the causal effect? Determining whether we can measure causation from association is known as identification analysis.

We must check whether there were any conditions under which the measure of association, $$S$$, equals the measure of causation, $$ACE$$. As a matter of fact, this would be the case if the sub-populations were comparable with respect to all confounders, i.e., the factors that could also influence the outcome.

### Ignorability <a href="#h3_974053683" id="h3_974053683"></a>

Remarkably, the conditions under which we can measure causal effects from observational data are very similar to those that justify causal inference in randomized experiments. A pure random selection of treated and untreated individuals does indeed remove any potential selection bias and leaves the confounding factor distributions identical in the sup-populations, thus allowing the estimation of the effect of the treatment alone. This condition is known as “ignorability,” which can be formally written as:

$$({Y_1},{Y_0}) \bot A$$

This means that the potential outcomes, $$Y_1$$, and $$Y_0$$ must jointly be independent of the treatment assignment, $$A$$. This condition of ignorability holds in an ideal experiment. Unfortunately, this condition is very rarely met in observational studies. However, conditional ignorability may hold, which refers to ignorability within subgroups of the domain defined by the values of $$X$$ (note that $$X$$ can be a vector).

In words, conditional on variables $$X$$, $$Y_1$$, and $$Y_0$$ are jointly independent of $$A$$, the assignment mechanism. If conditional ignorability holds, we can utilize the estimator, $$S|X$$, to estimate the average causal effect, $$ACE|X$$.

$$\eqalign{ & ACE|X = E[{Y_1}|X] - E[{Y_0}|X] \cr & = E[{Y_1}|A,X] - E[{Y_0}|A,X] \cr & = E[Y|T = 1,X] - E[Y|T = 0,X] \cr & = S|X \cr}$$

How can we select the correct set of variables $$X$$ among all variables in a system? How do we know that such variables $$X$$ are observed or even exist in a domain? This is what makes the concept of ignorability highly problematic in practice. Pearl (2009) states:

> The difficulty that most investigators experience in comprehending what “ignorability” means, and what judgment it summons them to exercise, has tempted them to assume that it is automatically satisfied, or at least is likely to be satisfied if one includes in the analysis as many covariates as possible. The prevailing attitude is that adding more covariates can cause no harm (Rosenbaum 2002, p. 76) and can absolve one from thinking about the causal relationships among those covariates, the treatment, the outcome, and, most importantly, the confounders left unmeasured (Rubin 2009).

The absence of hard-and-fast criteria makes ignorability a potentially dangerous concept for practitioners.
