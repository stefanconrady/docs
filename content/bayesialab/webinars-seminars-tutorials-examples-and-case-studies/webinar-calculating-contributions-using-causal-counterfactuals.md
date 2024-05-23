---
description: Stefan Conrady, Bayesia USA
---

# Webinar: Calculating Contributions Using Causal Counterfactuals

### Context & Motivation&#x20;

Attribution and contribution often appear in a similar context, and both concepts are closely related to causality. In general, attribution identifies the cause of an observed outcome. In the marketing domain, however, attribution has a somewhat unique interpretation and often refers to the origin of a consumer’s journey toward a purchase. In this particular context, observed outcomes are attributed to specific prior touchpoints, such as website visits or ad clicks.

On the other hand, contribution, as the name implies, refers to the confluence of multiple factors or causes with regard to an effect. In the marketing context, multiple advertising campaigns and promotions, beyond just single touchpoints, would contribute to sales, for instance. So, the definition of contribution is reasonably straightforward.

The decomposition and quantification of the contributing causes is the problem. Plus, this challenge is not new, as this quote from the late 19th century suggests: “Half the money I spend on advertising is wasted; the trouble is, I don’t know which half” (no pun intended, but the attribution of this quote is uncertain). In other words, we do not know how promotional activities contribute to the outcome, i.e., sales. Conversely, calculating the contributions means that we proportionally allocate a given outcome to any number of potential causes.

### Calculating Contributions&#x20;

While contribution appears to be rather straightforward in conceptual terms, a mathematical definition is not nearly as obvious.

We propose distinguishing between two types of contributions, which we shall call Type 1 and Type 2 Contributions. Both types rely on computing the difference between factual and counterfactual outcomes corresponding to factual and counterfactual conditions of multiple causes.

A factual outcome is simply an actual observation of an outcome, e.g., sales. Associated with a factual outcome are multiple causes at their observed, factual levels. A counterfactual outcome results from causes being set to hypothetical, counterfactual conditions. This begs the question of how we can calculate a counterfactual outcome. We need to calculate the counterfactual outcome by simulating a counterfactual intervention using a causal model. In our case, we use a Bayesian network, which provides numerous advantages for our purposes.

### A Fictional Example&#x20;

We introduce an elementary fictional domain with three causes and one outcome as an example. In fact, we make up the “laws of nature” and, thus, have perfect knowledge of this data-generating process (DGP).

From this generated data, we then machine-learn a Bayesian network that approximates the joint probability distribution of the data as if we did not know the DGP. By default, of course, any machine-learned network would be non-causal. However, by utilizing VanderWeele’s Disjunctive Cause Criterion for confounder selection, we can indeed utilize the learned Bayesian network for causal inference. Hence, we can simulate the effect of setting all three causes to counterfactual states. That choice, however, requires making assumptions from expert knowledge.

In this webinar, we perform machine learning with BayesiaLab and use its Likelihood Matching algorithm for causal inference computations. In addition to calculating contributions, we can determine the “baseline level” of the outcome variable and estimate synergies (positive and negative) between multiple causes.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692193294/2019-06-26-Contribution-Analysis_naq7uh.mp4" %}

### Presentation Materials&#x20;

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109035/csv\_v1imah.svg) Synthetic Dataset.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692126623/Synthetic\_Dataset\_iv63mn.csv)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) Bayesian Network Model for Contribution Analysis.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692126658/Bayesian\_Network\_Model\_for\_Contribution\_Analysis\_qzkefr.xbl)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109037/pdf\_do9ray.svg) 2019-06-26-Contribution-Analysis.pdf](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692126701/2019-06-26\_Contribution\_Analysis\_uml5kv.pdf)

### About the Presenter

Stefan Conrady has over 20 years of experience in decision analysis, analytics, market research, and product strategy with Mercedes-Benz, BMW Group, Rolls-Royce Motor Cars, and Nissan, which included assignments in North America, Europe, and Asia.

Today, in his role as Managing Partner of Bayesia USA and Bayesia Singapore, he is recognized as a thought leader in applying Bayesian networks for research, analytics, and reasoning.

Recently, Stefan and his colleague Dr. Lionel Jouffe co-authored [Bayesian Networks & BayesiaLab — A Practical Introduction for Researchers](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/book), which is now available as an e-book.
