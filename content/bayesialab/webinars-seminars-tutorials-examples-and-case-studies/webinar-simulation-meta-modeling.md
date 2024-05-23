---
description: Stefan Conrady, Bayesia USA
---

# Webinar: Simulation-Meta-Modeling

### Context & Motivation: Simulations, Fast and Slow&#x20;

Given the cost and technical challenges of experimenting with real physical systems, it is common practice in engineering to approximate such domains with computer models. These models incorporate the physical laws, typically in the form of hundreds of differential equations, that govern the system's real-world behavior. That way, the system performance can be examined in detail before building a hardware prototype. Simulations allow engineers to try out different parameters of components in pursuit of performance objectives while taking into account constraints.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/2019-02-13-Simulation-Meta-Modeling/shutterstock_530777935_1200x628.jpg" alt="" width="375"><figcaption></figcaption></figure>

While increasing computing power has made simulations more accessible and affordable than ever, performance remains a significant constraint. Why? For each set of parameter values, a new simulation must be run, in which many differential equations need to be solved. While this might only take a few seconds on modern computers, one generally needs to test many levels of many parameters, which would require thousands or even millions of iterations.

So, as the computing requirements grow exponentially with the number of parameters and levels, alternative strategies must be sought. One approach would be to be very selective in terms of which parameters and levels to test, i.e., narrowing the search space by utilizing a search algorithm.

### Simulating the Simulation&#x20;

In our webinar, we pursue a different strategy. We approximate the original simulation model, which is based on differential equations, with another model, a so-called meta-model. In effect, we are simulating the simulation of the real-world system. This approach is generally known as Response Surface Methodology, in which the relationships between parameters and target variables are approximated with functions that are unrelated to the underlying physical laws.

In our case, we machine-learn a Bayesian network meta-model from previously computed simulation data and, thus, capture the relationships between parameters and target variables entirely nonparametrically. With such a meta-model, we can perform inference much faster and see the effect of parameter changes in real-time.

In our case study, we examine the impact of tire stiffness, spring rates, and damping constants on the ride comfort of vehicle passengers. We create a so-called "quarter-vehicle model" using a two-mass spring/damper system in Modelica. On that basis, we simulate the vehicle's response to vertical excitations from a synthesized, irregular road surface. This produces the sample observations we need for learning a Bayesian network model with BayesiaLab.

### Analysis in the Frequency Domain&#x20;

Bayesian networks offer another key advantage in that variables can represent distributions in the frequency domain. This allows for a direct evaluation of the impact of parameter changes on the frequency response of the vertical vehicle body acceleration. This frequency response will be our principal measure for judging ride quality and body control. Generally speaking, we want to minimize peaks in the frequency range between 0 Hz and 200 Hz.

In this context, computing the frequency response curve's [entropy](../key-concepts/entropy/), an information-theoretic measure, is very helpful. For instance, BayesiaLab's built-in optimization algorithms can search for parameter values that minimize the entropy of the frequency response, i.e., make the curve as uniform as possible.

### Meta-Models in Your Head&#x20;

Meta models are ultimately shortcuts for a faster system evaluation. As it turns out, we implicitly use meta-models in the qualitative evaluation of systems all the time. Reasoning about a vehicle suspension, we would presumably argue that "softer spring and damper settings" generally provide a "smoother ride," and we could make such a (correct) statement entirely without solving any differential equations.

### Related Examples&#x20;

A recent presentation by Zack Xuereb Conti on simulation meta-modeling with Bayesian networks provided the impetus for developing this case study.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692193876/Simulation_Meta-Modeling_with_Bayesian_Networks_pulam7.mp4" %}

### Presentation Materials&#x20;

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) Simulation Meta-Model.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692145593/Bayesian\_Network\_Simulation\_Meta-Model\_i13w7j.xbl)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109037/pdf\_do9ray.svg) 2019-02-21-Simulation-Meta-Modeling.pdf](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692145602/2019-02-21-Simulation-Meta-Modeling\_vovfel.pdf)

### About the Presenter

Stefan Conrady has over 20 years of experience in decision analysis, analytics, market research, and product strategy with Mercedes-Benz, BMW Group, Rolls-Royce Motor Cars, and Nissan, which included assignments in North America, Europe, and Asia.

Today, in his role as Managing Partner of Bayesia USA and Bayesia Singapore, he is recognized as a thought leader in applying Bayesian networks for research, analytics, and reasoning.

Recently, Stefan and his colleague Dr. Lionel Jouffe co-authored [Bayesian Networks & BayesiaLab — A Practical Introduction for Researchers](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/), which is now available as an e-book.
