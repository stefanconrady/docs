# Bayes' Rule (Bayes' Theorem)

### Context

> “Bayesian inference is important because it provides a normative and general-purpose procedure for reasoning under uncertainty.”
>
> Inductive Reasoning: Experimental, Developmental, and Computational Approaches, edited by Aidan Feeney and Evan Heit

Bayesian inference refers to an approach first proposed by [Rev. Thomas Bayes](https://en.wikipedia.org/wiki/Thomas\_Bayes) (1702-1761), whose rule allows calculating the probability of an event A upon observing an event B.

### Bayes' Rule

Bayes' rule or Bayes’ theorem relates the conditional and marginal probabilities of events A and B (provided that the probability of B is not equal to zero). More specifically, Bayes' rule allows calculating the conditional probability of event A given event B with the inverse conditional probability of event B given event A.

$$
P(A|B) = P(A) \times {{P(B|A)} \over {P(B)}}
$$

#### Posterior

$$
P(A|B)
$$

is the conditional probability of event A given event B. It is also called the "posterior" probability because it depends on knowledge of event B. This is the probability of interest.

{% hint style="info" %}
Note that referring to "posterior" should not be interpreted in a temporal sense, i.e., it does not imply a temporal order between events A and B.
{% endhint %}

#### Prior

$$
P(A)
$$

is the prior probability (or “unconditional” or “marginal” probability) of event A. The unconditional probability P(A) was first called “a priori” by [Sir Ronald A. Fisher](https://en.wikipedia.org/wiki/Ronald\_Fisher). It is a “prior” probability because it does not consider any information about event B.

$$
P(B)
$$

is the prior or marginal probability of event B.

{% hint style="info" %}
Note that "prior," just like "posterior," does not imply a temporal order.
{% endhint %}

#### Likelihood Ratio <a href="#h3_1752380299" id="h3_1752380299"></a>

$$
{{P(B|A)} \over {P(B)}}
$$

is the Bayes factor or likelihood ratio.

### Learn More

* [Chapter 4: Knowledge Modeling & Probabilistic Reasoning](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-4-knowledge-modeling-and-probabilistic-reasoning.md)
