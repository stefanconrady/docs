---
description: Dr. Lionel Jouffe, Bayesia S.A.S. & Stefan Conrady, Bayesia USA
---

# Tech Talk: Epidemic Modeling with Bayesian Networks

### BayesiaLab Tech Talk Overview&#x20;

Compartmental models represent the most common approach for characterizing the development of an epidemic. In an earlier webinar, we introduced a compartmental S-I-R-D model and created a highly-simplified Bayesian network to illustrate the principles. Given its great relevance, we believe the topic warrants a more detailed explanation beyond the initial "toy model."

For the purpose of this BayesiaLab Tech Talk, we present a more comprehensive S-E-I-R-D model. Each letter denotes a compartment (or state) of individuals in a population:

* S: number of susceptible
* E: number of exposed
* I: number of infected
* R: number recovered
* D: number of dead

Additionally, we further differentiate within the states of exposed and infected to account for contagiousness and disease severity.

In standard models, a set of differential equations describes how individuals move between the compartments/states. In this Tech Talk, we implement the differential equations as probabilistic, temporal relationships between nodes in a Bayesian network.

While we often use fictional values in webinars to emphasize methodology over the subject matter, we take a different approach here: The numerical values and parameters presented in this Tech Talk are derived from current COVID-19 observations in France. As a result, the model attempts to represent the actual pandemic situation in France and forecast the pandemic progression.

### Presentation Video&#x20;

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692058721/BayesiaLab_Tech_Talk__Epidemic_Modeling_with_Bayesian_Networks_co0uxp.mp4" %}

### Presentation Materials&#x20;

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109037/pdf\_do9ray.svg) S2E3IRD.pdf](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692058736/S2E3IRD\_acafw9.pdf)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) S2E3IRD\_France\_h2\_Scenarios.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692058860/S2E3IRD\_France\_h2\_Scenarios\_hqgijj.xbl)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) SEIRD\_d.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692058869/SEIRD\_d\_yawgmg.xbl)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) SEIRD\_h.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692058881/SEIRD\_h\_ajjhsy.xbl)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036393/py\_nss0ct.svg) OptimizationSEIRD\_OptADR.py](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692058894/OptimizationSEIRD\_OptADR\_mgs9jd.py)

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036393/py\_nss0ct.svg) SEIRD.py](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692058903/SEIRD\_xmyqzk.py)
