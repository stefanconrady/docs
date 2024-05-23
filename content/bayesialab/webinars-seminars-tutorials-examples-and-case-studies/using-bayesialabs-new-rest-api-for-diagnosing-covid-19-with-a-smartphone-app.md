---
description: Dr. Lionel Jouffe, Bayesia S.A.S. & Stefan Conrady, Bayesia USA
---

# Using BayesiaLab's New REST API for Diagnosing COVID-19 with a Smartphone App

### Summary

In this webinar, Dr. Lionel Jouffe, Bayesia's CEO, explains all the development steps from the initial medical knowledge elicitation to releasing a smartphone app for diagnostic decision support — all within the framework of Bayesian networks and BayesiaLab. In this context, you will learn about Bayesia's new REST API and how it can make inferences with Bayesian networks available to any application.&#x20;

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1686700040/Videos/dmbjte6voptd4weely7j.mp4" %}

### Background & Motivation&#x20;

Over the past 12 months, the growing number of COVID-19 infections has led to an urgent need for the reliable detection of new infections. Given the similarity of their symptoms, the common cold, influenza, and COVID-19 have remained difficult to differentiate.

In this context, the Bayesia team has been at the forefront of developing diagnostic expert systems for COVID-19 using the Bayesian network framework. In March 2020, we assembled a working group of medical researchers, epidemiologists, and clinicians to develop a Bayesian network for distinguishing COVID-19 from other respiratory infections. Since then, we have maintained a public [WebSimulator](https://www.bayesia.com/articles/bayesialab-knowledge-hub/2021-03-10-tech-talk-bayesia-diagnostic-app/a/WebSimulator) and continuously updated it with the latest understanding of the evolving pandemic.

Bayesian networks are recognized as powerful tools for risk analysis and decision support and have become a popular model for clinical decision support systems (CDSS). Bayesian networks are particularly suitable for healthcare as they can

1. model complex problems with causal dependencies under high degrees of uncertainty;
2. combine different sources of information, including empirical data and expert opinion;
3. have an interpretable graphical structure;
4. model interventions in diagnostic and prognostic ways.&#x20;

Based on the success of the COVID-19 WebSimulator implementation, we joined forces with Dr. Jordi Ochando at the Spanish Society for Immunology and Dr. Manisha Brahmachary at the Mount Sinai School of Medicine to further refine our web-based diagnostic tool and turn it into an app for iOS and Android. Numerous medical research institutes collaborated in our efforts, including Hôpital Foch (France), the University of Mons (Belgium), and the Hospital Universitario Donostia (Spain).&#x20;

### Medical Knowledge Elicitation with BEKEE&#x20;

We present the [Bayesia Expert Knowledge Elicitation Environment (BEKEE)](https://www.bayesia.com/articles/bayesialab-knowledge-hub/bayesia-expert-knowledge-elicitation-environment) as a platform for compiling and encoding knowledge from domain specialists. This workflow aggregates the available medical knowledge into a Bayesian network, which is an updatable expert system. Clinicians and patients can then access the Bayesian network expert system through various interfaces, such as the [BayesiaLab WebSimulator](https://www.bayesia.com/articles/bayesialab-knowledge-hub/websimulator) or the [SEI Smartphone App](https://www.bayesia.com/articles/bayesialab-knowledge-hub/2021-03-10-tech-talk-bayesia-diagnostic-app/a/h2\_1874493526).

### The Bayesia WebSimulator&#x20;

The [BayesiaLab WebSimulator](https://www.bayesia.com/articles/bayesialab-knowledge-hub/websimulator) has become a popular platform for publishing BayesiaLab models via a web interface to any audience, from local collaborators to the general public. This way, researchers can provide access to a newly-developed Bayesian network so that anyone with an Internet connection can use that model for simulation.

### The Bayesia Engine API&#x20;

At the core of the [BayesiaLab WebSimulator](https://www.bayesia.com/articles/bayesialab-knowledge-hub/websimulator) is the [Bayesia Engine API](https://www.bayesia.com/articles/bayesialab-knowledge-hub/bayesia-engine-api), which allows you to access the learning and inference functions of BayesiaLab programmatically. As of the beginning of 2021, we've also made this API available as a RESTful service. Your program code can make an HTTP call to Bayesia's API server to perform inference on a Bayesian network model.

### The SEI Smartphone App&#x20;

For the first implementation of Bayesia's new [REST API](https://www.bayesia.com/articles/bayesialab-knowledge-hub/bayesia-engine-rest-api-inference) in a smartphone app, it was an obvious choice for our team to create a COVID-19 diagnostic tool, building on our existing research. This new app allows individuals to perform a COVID-19 self-assessment guided by BayesiaLab's Adaptive Questionnaire algorithm. Since its launch in February, the app has already produced tens of thousands of assessments based on self-reported symptoms.

You can install the app via the following links:

* For Android: [https://play.google.com/store/apps/details?id=com.seicov.app\&hl=en\_US\&gl=US](https://play.google.com/store/apps/details?id=com.seicov.app\&hl=en\_US\&gl=US)
* For iOS: [https://apps.apple.com/us/app/sei/id1534832266](https://apps.apple.com/us/app/sei/id1534832266)

### Webinar Materials

[TechTalk\_SEICov.pdf](https://www.bayesia.com/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/2021-03-10-COVID-Diagnostics/TechTalk\_SEICov.pdf)
