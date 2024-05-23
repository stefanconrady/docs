# Adjustment Formula

How can we translate the abstract concept of Graph Surgery into something that can compute actual numerical values? In fact, we can work directly with graphs — in the form of Bayesian networks — and use BayesiaLab to perform Graph Surgery and simulate interventions.&#x20;

However, before we illustrate that in the next section of this chapter, we want to formally conclude the line of reasoning that connects the pre-intervention distribution P to the post-intervention distribution Pm and introduce the Adjustment Formula. We paraphrase Pearl, Glymour, and Jewell (2016), p. 56f. to develop this formula.

In our example, we can easily estimate the pre-intervention distribution P from the available data, but we need the post-intervention distribution Pm to calculate the causal effect. The key lies in recognizing that Pm shares two essential properties with P.

First, the marginal distribution$$P(Z=z)$$ remains invariant under the intervention because the process of determining Z is unaffected by removing the arc Z → X. In our example, this means that the share of men and women must remain the same before and after the intervention:

$${P_m}(Z = z) = P(Z = z)$$

Secondly, the conditional probability distribution $$P(Y=y|Z=z, X=x)$$ remains invariant under the intervention because the process that determines how Y responds to X and Z stays the same, regardless of whether X changes naturally or through external intervention. We can state this formally as follows:

$${P_m}(Y = y|Z = z,X = x) = P(Y = y|Z = z,X = x)$$

Furthermore, X and Z are marginally independent in the mutilated graph. This means that the conditional probability distribution of Z given X in the mutilated graph is the same as the marginal probability distribution of Z in the pre-intervention graph:

$${P_m}\left( {Z = z|X = x} \right) = {P_m}\left( {Z = z} \right) = P\left( {Z = z} \right)$$

Since the Adjustment Criterion is satisfied in the mutilated graph, we have the following:

$$P(Y = y|do(X = x)) = {P_m}(Y = y|X = x)$$

By conditioning on Z and summing over all values z, we obtain:

$$P(Y = y|do(X = x)) = \sum\limits_z {{P_m}(Y = y|X = x,Z = z){P_m}(Z = z|X = x)}$$

Furthermore, X and Z are independent in the mutilated graph:

$$P(Y = y|do(X = x)) = \sum\limits_z {{P_m}(Y = y|X = x,Z = z){P_m}(Z = z)}$$

Using the two invariance equations above, we obtain what is known as the Adjustment Formula. It expresses the post-intervention distribution exclusively in terms of the pre-intervention distribution:

$$P(Y = y|do(X = x)) = \sum\limits_z {P(Y = y|X = x,Z = z)P(Z = z)}$$

The Adjustment Formula computes the association between X and Y for each value z (or strata of z∈Z) and then produces a weighted average. On this basis, we can now estimate the Average Causal Effect (ACE):

$$ACE = P\left( {Y = 1|do(X = 1)} \right) - P\left( {Y = 1|do(X = 0)} \right)$$

{% hint style="info" %}
We know that by performing a randomized experiment, we obtain an unbiased estimate of the causal effect of the treatment. More specifically, through randomization, we randomly split the patient population into two sub-populations and forced the first group to receive treatment, and withheld the treatment from the second group. Through the random assignment of the treatment, we ensure that there is no association between Z and X. Also, all other properties remain unaffected by the randomization of treatment, including the distribution of Z, the relationship between Z and Y, and the relationship between X and Y.

As a result, graph surgery can be seen as a “randomization after the fact.” However, we need to realize that performing graph surgery can only achieve quasi-randomization with regard to observed and known confounders, in our case Z. A randomized experiment, however, can make treatment independent of all other confounders, observed, unobserved, and unknown. Thus, randomized experiments remain the gold standard for establishing causal effects.

All our efforts in estimating causal effects through adjustment or graph surgery are merely an attempt to mimic the properties of a randomized experiment. Unfortunately, we can never measure how close we are to achieving this goal. We can only be disciplined with our assumptions and make a causal claim based on that.
{% endhint %}

**Simpson’s Paradox Resolved**

Returning to Simpson’s Paradox, the equation

$$P(Y = y|do(X = x)) = \sum\limits_z {P(Y = y|X = x,Z = z)P(Z = z)}$$

gives us the answer to our question of whether we need to look at the aggregate data table or the gender-specific data table for determining the true causal effect of treatment on the outcome: “Conditioning on Z and summing over all values z” means that we need to utilize the gender-specific table. More specifically, we need to compute the association between X and Y for each value of Z, i.e., each stratum of z ∈ Z, and then calculate the weighted average. This estimation method is also known as stratification.

**Aggregate Table**

| <p><br></p> | Patient Recovered |     |
| ----------- | ----------------- | --- |
| Treatment   | Yes               | No  |
| Yes         | 50%               | 50% |
| No          | 40%               | 60% |

**Gender-Specific Table**

| <p><br></p> | <p><br></p> | Patient Recovered |     |
| ----------- | ----------- | ----------------- | --- |
| Gender      | Treatment   | Yes               | No  |
| Male        | Yes         | 60%               | 40% |
| No          | 70%         | 30%               |     |
| Female      | Yes         | 20%               | 80% |
| No          | 30%         | 70%               |     |

$$\begin{array}{l} ACE = P(Y = 1|do(X = 1)) - P(Y = 1|do(X = 0))\\ = (P(Y = 1|X = 1,Z = 0)P(Z = 0) + P(Y = 1|X = 1,Z = 1)P(Z = 1))\\ - (P(Y = 1|X = 0,Z = 0)P(Z = 0) + P(Y = 1|X = 0,Z = 1)P(Z = 1))\\ = (0.2 \times 0.5 + 0.6 \times 0.5) - (0.3 \times 0.5 + 0.7 \times 0.5)\\ = - 0.1 \end{array}$$

The ACE turns out to be negative, i.e., it has the opposite sign of what we would have inferred by merely looking naively at the association between treatment and outcome. This illustrates that a bias in the estimation of an effect can be more than just a nuisance for the analyst. Bias can reverse the sign of the effect! In our example, the treatment under study would kill people instead of healing them. The good news is that we have a theory stipulating that gender is a confounder, and this variable is observed. If it were not recorded in our dataset (hidden variable), we would not be able to compute the causal effect of treatment. We can also imagine situations where we do not know that confounders exist and, therefore, do not measure them. This can lead to substantially wrong estimations of causal effects and lead to policies with catastrophic consequences. &#x20;
