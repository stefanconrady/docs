# The Back-Door Criterion

### Context

Causal effect estimation is the topic of [Chapter 10 in our book, Bayesian Networks & BayesiaLab](../../../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-10-causal-effect-identification-and-estimation/). In this context, we discuss the central role of confounders and non-confounders in identifying and estimating causal effects. Much of what we explain in that chapter is a practical illustration of Judea Pearl's teaching on causality.&#x20;

As the originator of an entire school of thought on causality, Judea Pearl is certainly at liberty to take a more light-hearted and playful approach in presenting this serious topic. Chapter 4 in The Book of Why he titled "Confounding and Deconfounding: Or, Slaying the Lurking Variable." In fact, Pearl presents the task of "deconfounding" for causal effect estimation as a series of "games," which we now wish to illustrate with Bayesian networks.&#x20;

### The Back-Door Criterion and Deconfounding — It's All Fun and Games

We begin with a selection of quotes from the beginning of Chapter 4 to provide motivation for the forthcoming examples.

> "To understand the back-door criterion, it helps first to have an intuitive sense of how information flows in a causal diagram. I like to think of the links as pipes that convey information from a starting point X to a finish Y. Keep in mind that the conveying of information goes in both directions, causal and noncausal, as we saw in Chapter 3.
>
> In fact, the noncausal paths are precisely the source of confounding."
>
> "To deconfound two variables X and Y, we need only to block every noncausal path between them without blocking or perturbing any causal paths."
>
> "With these rules, decounfounding becomes so simple and fun that you can treat it like a game"
>
> [Pearl, Judea. The Book of Why: The New Science of Cause and Effect (pp. 158-159). Basic Books. Kindle Edition.](https://amzn.to/322imYl)

For each of the proposed games in Chapter 4, we prepare a corresponding Bayesian network in BayesiaLab. These networks allow you to experiment with the "pipes that convey information" as if they were set up in a laboratory, where you can look inside the tubes and measure the flows in pipes:
