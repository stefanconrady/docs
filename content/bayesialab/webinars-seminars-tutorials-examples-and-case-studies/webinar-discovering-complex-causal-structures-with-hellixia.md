---
description: Dr. Lionel Jouffe & Stefan Conrady
cover: >-
  https://images.unsplash.com/photo-1421789497144-f50500b5fcf0?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxmbGlnaHQlMjBkZWxheXxlbnwwfHx8fDE3MDQ3MjkzNjF8MA&ixlib=rb-4.0.3&q=85
coverY: 0
---

# 🆕 Webinar: Discovering Complex Causal Structures with Hellixia

#### Recorded on January 25, 2024, 16:00 (UTC)

In this webinar, you'll learn about a new approach to causality analysis using Bayesian networks. We will showcase the innovative causal analysis features of [Hellixia, BayesiaLab's new subject matter assistant](../hellixia-user-guide/). All of these new Hellixia features are part of BayesiaLab 11.2, which is now available.

### Webinar Recording

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1711043771/Discovering_Complex_Causal_Structures_with_Hellixia_kawdna.mp4" %}

### Introduction

Whether you're a data scientist, researcher, or analytics professional, understanding the causal direction between variables is critical to fully understanding a given problem domain. However, despite many advances in machine learning in recent years, discovering causalities purely from data remains elusive.



{% embed url="https://res.cloudinary.com/dvr3obmlj/image/upload/v1704417995/Delays_in_scheduled_flight_departures_4_bb7x7o_kaekap.webp" %}

### Context & Background

#### Where is my Bag?

You may be familiar with our ["Where is my bag?"](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-4-knowledge-modeling-and-probabilistic-reasoning.md) example, which received much publicity through Judea Pearl's best-selling book, The Book of Why. This example was about correctly reasoning about the probability of receiving a piece of checked luggage after landing at a destination airport.&#x20;

The key to dealing with this problem was encoding our limited causal knowledge into a Bayesian network, which then allowed us to perform inference correctly. In other words, we provided our knowledge, and then the computer, i.e., the BayesiaLab software, could reason for us.

#### Flight Departure Delays

Today, we once again use an example from the field of air travel. Now, we are interested in the causes and consequences of flight delays. However, we are not relying on any knowledge we might already have to build a Bayesian network model. Instead, we leverage BayesiaLab's new [subject matter assistant, Hellixia](../hellixia-user-guide/), to assemble any knowledge that may be accessible through Large Language Models, such as ChatGPT.

### Webinar Agenda

#### Pairwise Causal Links

To explore the topic of flight delays, we start by evaluating pairwise relationships between variables that are presumably relevant, such as "Holidays" and "Flight Delays" or "Flight Delays" and "Flight Safety."

Without using any data from which a network could potentially be machine-learned, Hellixia utilizes Large Language Models to investigate the presence of causal relationships between selected pairs of variables. This feature determines whether a causal link exists and provides an estimated measure of causal effect, including both positive and negative impacts.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1704562381/PCL_vjbjvy.webp" alt="" width="375"><figcaption></figcaption></figure>

#### Causal Structural Priors

Establishing causality requires much more than discovering associations between variables. It requires that we identify the correct direction and the nature of the influence between the variables of interest. Hellixia can directly tap into the subject matter expertise contained in Large Language Models and use that knowledge to assign causal structural priors to a set of selected arcs. BayesiaLab's Structural Learning algorithms can then use these priors to machine-learn causal Bayesian Networks.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1704562452/SP1_w9r5wi.webp" alt="" width="375"><figcaption></figcaption></figure>

#### Causal Arc Explainer

Once causal directions have been established for specific arcs within a Bayesian network, it becomes important to communicate their meaning to stakeholders. Hellixia can elaborate on the causal mechanisms represented by arcs in the Bayesian network, thereby helping stakeholders understand the underlying causal processes.

In our example about flight delays, Hellixia would add comments to the causal arcs shown in the following network, which includes variables such as Crew Availability, Air Traffic, Flight Scheduling, and Passenger Boarding.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1704562538/CAE_jlxdds.webp" alt="" width="188"><figcaption></figcaption></figure>

#### Causal Network Generator

Creating a new Bayesian network of a complex domain exclusively from human expert knowledge can be challenging and time-consuming. In this webinar, we'll demonstrate how Hellixia can substantially simplify and accelerate this process. Given a particular variable of interest as a starting point, Hellixia can automatically create nodes and build a comprehensive and fully specified Bayesian network representing the problem domain. Fully specified means that both the causal network structure and the parameters are obtained by Hellixia. As a result, experts can review and build upon such a Hellixia-generated model instead of having to start from zero.

In our example domain, the starting point is "Delays in Scheduled Flight Departures." Hellixia finds causes, such as "Air Traffic" and "Weather Conditions," as well as consequences, e.g., "Passenger Satisfaction" and "Operational Costs."

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1704562610/CNG_oryk73.webp" alt="" width="375"><figcaption></figcaption></figure>

#### Causal Relationship Finder

In addition to building a causal Bayesian network from scratch, like with the [#causal-network-generator](webinar-discovering-complex-causal-structures-with-hellixia.md#causal-network-generator "mention") function above, we can use Hellixia to create a causal Network from a defined set of variables (e.g., created with Hellxia's Dimension Elicitor).

Here, we provide a set of causes and consequences and let Hellixia determine how they are causally related.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1704562667/CRF_kjwpsi.webp" alt="" width="375"><figcaption></figcaption></figure>

### About the Presenter

* Dr. Lionel Jouffe is co-founder and CEO of France-based Bayesia S.A.S. Lionel holds a Ph.D. in Computer Science from the University of Rennes and has worked in Artificial Intelligence since the early 1990s. While working as a Professor/Researcher at ESIEA, Lionel started exploring the potential of Bayesian networks.
* After co-founding Bayesia in 2001, he and his team have been working full-time on the development of BayesiaLab. Since then, BayesiaLab has emerged as the leading software package for knowledge discovery, data mining, and knowledge modeling using Bayesian networks. It enjoys broad acceptance in academic communities, business, and industry.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1710353058/PhotoLionel_bnmsdw.webp" alt="" width="188"><figcaption><p>Dr. Lionel Jouffe</p></figcaption></figure>

### Recordings of Previous Webinars

{% content-ref url="webinar-harnessing-hellixia-innovations-in-bayesian-belief-network-construction.md" %}
[webinar-harnessing-hellixia-innovations-in-bayesian-belief-network-construction.md](webinar-harnessing-hellixia-innovations-in-bayesian-belief-network-construction.md)
{% endcontent-ref %}

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}

### Upcoming BayesiaLab Events

{% content-ref url="../bayesialab-conferences/2024-bayesialab-spring-conference-april-11-12-2024/" %}
[2024-bayesialab-spring-conference-april-11-12-2024](../bayesialab-conferences/2024-bayesialab-spring-conference-april-11-12-2024/)
{% endcontent-ref %}

{% content-ref url="../academy-courses-events-seminars-and-webinars/introductory-bayesialab-course.md" %}
[introductory-bayesialab-course.md](../academy-courses-events-seminars-and-webinars/introductory-bayesialab-course.md)
{% endcontent-ref %}

{% content-ref url="../academy-courses-events-seminars-and-webinars/advanced-bayesialab-course.md" %}
[advanced-bayesialab-course.md](../academy-courses-events-seminars-and-webinars/advanced-bayesialab-course.md)
{% endcontent-ref %}
