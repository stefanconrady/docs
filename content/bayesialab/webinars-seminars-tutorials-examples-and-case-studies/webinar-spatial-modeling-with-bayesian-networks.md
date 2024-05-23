---
description: Stefan Conrady, Bayesia USA
---

# Webinar: Spatial Modeling with Bayesian Networks

### A Different Math for Social Distancing&#x20;

These days, our daily movements are largely governed by "social distancing" mandates. Their purpose is self-explanatory, and following them is certainly the prudent thing to do.

Given the economic impact of keeping individuals apart, the question arises about what kind of distancing is most effective. How much worse is it, for instance, to have groups of 100 people versus groups of 10 in one place? What is the risk of traveling by bus compared to carpooling? How should employees be spaced across open-floor offices once work resumes?

This webinar will neither answer these specific questions nor provide policy recommendations. However, we will endeavor to provide a formal framework for reasoning about such questions.

### Distribution of Distances&#x20;

In this context, the distribution of distances between random points within a given space is very important. For example, if 1000 people were evenly distributed in a square hall, what would be the distribution of their distances, i.e., how many would be close together versus far apart? Unfortunately, the mathematical solution to this question is far from trivial. The distribution of distances l within a unit square is as follows:

$$P(l) = \left\{ {\begin{array}{*{20}{c}}   {2l\left( {{l^2} - 4l + \pi } \right)}&{0 \leqslant l \leqslant 1} \\    {2l\left( { - {l^2} - 4{{\tan }^{ - 1}}\left( {\sqrt {{l^2} - 1} } \right) + 4\sqrt {{l^2} - 1}  + \pi  - 2} \right)}&{1 < l \leqslant \sqrt 2 }  \end{array}} \right.$$

Presumably, the distances between individuals would be proportional to the probability of transmitting an infection. But that's a secondary question for now. First, we need to consider that individuals in groups are typically not evenly spaced. Secondly, environments can have any shape, although rectangles are very common. And, finally, people move about all the time. With that, an algebraic solution for the distribution of real-world distances between individuals seems unattainable.

### Bayesian Networks to the Rescue&#x20;

Bayesian networks can help with a fairly simple and intuitive solution to this problem. A simple Bayesian network with only five nodes can compute the same distributions as the complicated formula above.

In fact, with this network, we can compute the distributions for any arbitrary positioning of individuals in any type of space. For instance, we could take the U.S. population within the geographic bounds of the country and determine the distribution of distances between any two individuals, and all we need is the above network. Also, we can go beyond Euclidean distances and utilize the great-circle distance between points on the Earth's surface.

Our proposed approach will be the backbone of our discussion about "social distancing." It will allow us to quantify the effect of mandating or changing distances at different levels, similar to using signal filters for attenuating certain frequencies within a frequency range.

### Post-Pandemic Applications&#x20;

Beyond the current pandemic, there are presumably many other applications for this approach. We illustrated one of them in a recent webinar on Geographic Optimization with Bayesian Networks and BayesiaLab. One particular application was finding the optimal warehouse location given the distribution of manufacturing sites and end customers.

A key benefit of this methodology is that changing distributions does not require recalculating the distances of thousands of points. Rather, the Bayesian network can instantly perform inference given new inputs, thus allowing to simulate different configurations, such as desk arrangements in a classroom, etc. It opens up applications, such as maximizing the distances between seat assignments of airplane passengers.

### Focusing on BayesiaLab&#x20;

Compared to earlier webinars, we will emphasize the technical aspects of implementing the proposed methodologies with BayesiaLab. In this context, we will also cover foundational elements which may already be familiar to current BayesiaLab users. The objective is that you can replicate all examples presented in the webinar independently after the event.

### Presentation Video&#x20;

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692061406/Reasoning_Under_Uncertainty_Part_4___Spatial_Modeling_with_Bayesian_Networks_vd742t.mp4" %}

### Presentation Materials&#x20;

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109037/pdf\_do9ray.svg) 2020-04-30 Spatial Modeling.pdf](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692061902/2020-04-30\_Spatial\_Modeling\_gjwavh.pdf)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109035/csv\_v1imah.svg) Longitude\_Latitude\_Population.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692061918/Longitude\_Latitude\_Population\_fsq2qs.csv)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) Continental US Distance Distribution.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692061930/Continental\_US\_Distance\_Distribution\_evqrzu.xbl)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) Distances.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692061939/Distances\_bil8zs.xbl)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) Distances2.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692061946/Distances2\_uoxnus.xbl)

### About the Presenter

Stefan Conrady has over 20 years of experience in decision analysis, analytics, market research, and product strategy with Mercedes-Benz, BMW Group, Rolls-Royce Motor Cars, and Nissan, which included assignments in North America, Europe, and Asia.

Today, in his role as Managing Partner of Bayesia USA and Bayesia Singapore, he is recognized as a thought leader in applying Bayesian networks for research, analytics, and reasoning.

Recently, Stefan and his colleague Dr. Lionel Jouffe co-authored [Bayesian Networks & BayesiaLab — A Practical Introduction for Researchers](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/), which is now available as an e-book.

[\
](https://www.linkedin.com/in/stefanconrady/)
