---
description: >-
  This seminar was recorded on December 3, 2018, at the Virginia Tech Applied
  Research Center in Arlington, Virginia.
---

# Seminar: Knowledge Elicitation & Geopolitical Reasoning Under Extreme Uncertainty

### Context

In this workshop, we demonstrate how to elicit human knowledge for developing a high-dimensional computational model of an underlying problem domain in the form of a Bayesian network. This type of "Artificial Intelligence" allows us to reason formally—and quantitatively, despite the absence of numerical data—about the given issue.

As our case study topic, we examine a hypothetical geopolitical scenario that has the characteristics of actual events, such as the sinking of the Russian submarine Kursk in 2000 and the search for the Argentinian submarine San Juan in 2018. More specifically, we reason about the (fictional) disappearance of an American attack submarine in the disputed waters of the South China Sea. Our objective is to determine where and when to launch a search and rescue effort, if at all, given the risk of a military conflict with China.

### No Data = No Model = No Science?&#x20;

In this day and age of "Big Data," we may be led to believe that truth can only be established from data, especially in the context of a scientific inquiry. This is a misconception. Even without data, humans do possess knowledge, qualitative or quantitative, tacit or explicit, about many aspects of the world. We believe that a useful amount of knowledge exists regarding the conflict under study. Also, there is one particular type of knowledge that data on its own can never yield, and that is causality. For that, we always have to rely on human expertise.

### The Wisdom of Crowds&#x20;

Although there may not be a single expert among our seminar participants who can fully comprehend all the complexities of our case study topic, there may be several individuals who are more or less knowledgeable about different aspects of the conflict. It is our objective to break down the overall problem into numerous simpler questions, which are perhaps more easily "knowable," at least to some.

So, we are not looking for a single authoritative opinion. Rather, we are looking to collect and consolidate the full spectrum of thought, including causal relationships, from the seminar's participants. This is where the idea of the "wisdom of crowds" comes into play. We want attendees to provide their individual and independent assessments of different elements and relationships within the problem domain.

### Knowledge Elicitation with the Bayesia Expert Knowledge Elicitation Environment&#x20;

While the objective of collecting multiple opinions is straightforward, there are many technical and practical challenges in terms of implementing such a process. In the early days of the Cold War, the RAND Corporation proposed the so-called Delphi Method, which facilitated expert knowledge elicitation by iteratively querying stakeholders through a series of questionnaires that were distributed and collected by mail. After each round of questioning, the aggregated results were circulated for review and discussion, and all participating experts could further adjust their assessments based on the collective feedback. Needless to say, before the availability of electronic means of communication, such a process was tedious, bordering on the impractical.

### Reinventing the Delphi Method&#x20;

Today, we propose an entirely new, web-based approach, the [Bayesia Expert Knowledge Elicitation Environment (BEKEE)](broken-reference), which has the same objective as the original Delphi Method. In this seminar, we plan to use [BEKEE](broken-reference) to collect the opinions of the participants in real time from their own devices via a convenient web interface.

We shall see that systematically eliciting and encoding numerous pieces of (admittedly imperfect) knowledge into a Bayesian network can produce a remarkably useful approximation of the underlying domain, which provides us with a common framework for reasoning about policy options and evaluating their consequences.

### Reasoning Under Uncertainty&#x20;

Furthermore, by using a Bayesian network model, we can preserve all the uncertainty that exists in our collective knowledge and perform inference by consciously taking into account all the uncertainty. Thus, we manage to avoid two common and problematic extremes in reasoning, i.e., (i) suppressing uncertainty by calculating with the fake precision of single-point estimates, or (ii) being overwhelmed by uncertainty and abandoning quantitative reasoning altogether. A Bayesian network, however, can explicitly represent the uncertainty from the diversity of opinions captured via [BEKEE](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/bayesia-expert-knowledge-elicitation-environment).

Based on the newly generated Bayesian network, we can use BayesiaLab to reason probabilistically about the implications of various hypothetical interventions and simulate the outcomes of different policies.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1707403028/Knowledge_Elicitation_Geopolitical_Reasoning_Under_Extreme_Uncertainty_with_Bayesian_Networks_kycti5.mp4" %}

### Presentation Materials

{% embed url="https://res.cloudinary.com/dvr3obmlj/image/upload/v1707402645/2018-12-03-BEKEE-Geopolitical-Reasoning_tssco0.pdf?q=123" %}

### About the Presenter

Stefan Conrady has over 20 years of experience in decision analysis, analytics, market research, and product strategy with Mercedes-Benz, BMW Group, Rolls-Royce Motor Cars, and Nissan, which included assignments in North America, Europe, and Asia.

Today, as the Managing Partner of Bayesia USA and Bayesia Singapore, he is recognized as a thought leader in applying Bayesian networks for research, analytics, and reasoning.

Recently, Stefan and his colleague Dr. Lionel Jouffe co-authored [Bayesian Networks & BayesiaLab — A Practical Introduction for Researchers](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/), which is now available as an e-book.
