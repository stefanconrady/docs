# 🤝 Bayesia Expert Knowledge Elicitation Environment (BEKEE)

### Overview

Everybody is talking about "Big Data" and all its manifold opportunities. Very often, though, we hear almost as much about the challenges that come with this flood of data. Where to store it, how to analyze it, how to explain it, the list goes on and on. We think this is a very nice problem to have. Much more serious issues exist on the opposite end of the spectrum, where there is insufficient data. Unfortunately, all the advanced knowledge discovery algorithms fail in the absence of data.

In over ten years of continuous development and in increasingly sophisticated ways, BayesiaLab has permitted deriving knowledge from data through its machine learning algorithms, very much in the spirit of understanding "Big Data." However, BayesiaLab has maintained an equal focus on managing knowledge beyond measurable and countable data points, such as the knowledge in the human mind. BayesiaLab's graphical user interface has made it highly intuitive for individual subject matter experts to encode their own domain understanding into a Bayesian network, thus capturing what they explicitly or implicitly know. What is especially important, one can very easily and formally capture causal directions in a Bayesian network graph, which is something that few other frameworks can do.

However, when it comes to consolidating the collective knowledge from a group of experts rather than from an individual, the process is no longer as straightforward. Traditionally, one would perhaps bring the experts together in a brainstorming session and let them form a common understanding. Subsequently, such a consensus could be encoded manually. However, brainstorming sessions are prone to introducing a wide range of biases, which can be disastrously counterproductive in studying complex domains.

Bayesia Expert Knowledge Elicitation Environment, or BEKEE for short, is a web application designed to minimize detrimental group biases. The central idea is not to coerce consensus but to elicit everyone's individual views regarding the domain under study through the repeated use of questionnaires. The RAND Corporation first proposed such an approach in the 1950s, which became widely known as the Delphi Method.

To elicit probabilities, BEKEE queries stakeholders individually via an interactive questionnaire linked to the core BayesiaLab application. Retrieving expert views in such a fashion generates many "parallel universes" in domain understanding. These different perspectives can be formally compared by the facilitator and potentially returned to the group for a formal debate in the case of seriously conflicting assessments.

In most cases, this is an iterative process, and even if stakeholder opinions do not converge, BayesiaLab will compile all views and produce a unifying Bayesian network. This graph is now the mathematically correct summary of all the available expert opinions. As such, it can be utilized as a formal representation of the underlying domain. Most importantly, this graph is not merely a qualitative illustration. Instead, a Bayesian network is a fully computable model of the domain, which immediately facilitates the simulation of what-if scenarios.

We can evaluate this Bayesian network model similarly to a statistical model estimated from "Big Data." One might still prefer a data-based model if data were available, but in the absence thereof, the formally-encoded collective expert knowledge best represents what is known at the time.

### Knowledge Elicitation Workflow

The following illustrations are based on a real-world knowledge elicitation process on COVID-19 symptoms:

#### Conceptual Overview of Workflow

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1707943667/BEKEE-Upstream-Downstream_lebwep.svg){width="563"}

#### Step 1: Qualitative Knowledge Modeling in Brainstorming Session

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1707943667/BEKEE-Brainstorm_vvid5i.svg){width="563"}

#### Step 2: Quantitative Knowledge Elicitation

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1707943667/BEKEE-Quantitative-Elicitation_sr6byi.svg){width="563"}

#### Step 3: Deployment [](#h3_1184702896)

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1707943667/BEKEE-Deployment_bxou9n.svg){width="563"}

### Examples

- [Differential Diagnosis of COVID-19](../bayesialab/webinars-seminars-tutorials-examples-and-case-studies/webinar-differential-diagnosis-of-covid-19): This webinar introduces our collaborative knowledge elicitation project using BEKEE for the differential diagnosis of COVID-19 and influenza-like diseases.
- [Knowledge Elicitation & Geopolitical Reasoning Under Extreme Uncertainty with Bayesian Networks](../bayesialab/webinars-seminars-tutorials-examples-and-case-studies/seminar-knowledge-elicitation-and-geopolitical-reasoning-under-extreme-uncertainty): In this workshop, we demonstrate how to elicit human knowledge for developing a high-dimensional computational model of an underlying problem domain in the form of a Bayesian network. This type of "Artificial Intelligence" allows us to reason formally—and quantitatively, despite the absence of numerical data—about the given issue.

### Pricing

- For details on licensing fees, please see the BEKEE Price Guide.
