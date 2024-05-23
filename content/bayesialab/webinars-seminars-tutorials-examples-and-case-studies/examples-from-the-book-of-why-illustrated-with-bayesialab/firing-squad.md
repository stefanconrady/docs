# Firing Squad

### The Prisoner and the Firing Squad

> "Suppose that a prisoner is about to be executed by a firing squad. A certain chain of events must occur for this to happen. First, the court orders the execution. The order goes to a captain, who signals the soldiers on the firing squad (A and B) to fire. We’ll assume that they are obedient and expert marksmen, so they only fire on command, and if either one of them shoots, the prisoner dies."
>
> [Pearl, Judea. The Book of Why: The New Science of Cause and Effect (p. 40). Basic Books. Kindle Edition.](https://amzn.to/322imYl)

### The Problem as a Bayesian Network&#x20;

* We implemented Pearl's Firing Squad problem as a Causal Bayesian Network in BayesiaLab.
*   "Causal" means that the arc directions represent causal relationships between the nodes. \
    \
    \


    <figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Firing-Squad/FiringSquad0.svg" alt=""><figcaption></figcaption></figure>
* You can download this XBL file and open it with any version of BayesiaLab: \
  [BoW\_Firing Squad.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692033543/BoW\_Firing\_Squad\_xgeqi4.xbl)
* Alternatively, you can experiment with the Firing Squad model on this WebSimulator page: [https://simulator.bayesialab.com/#!simulator/211001563973](https://simulator.bayesialab.com/#!simulator/211001563973)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692035552/FiringSquadWebSimulator_dhvo2t.png" alt=""><figcaption></figcaption></figure>

### Question #1&#x20;

> "Using this diagram, we can start answering causal questions from different rungs of the ladder. First, we can answer questions of association (i.e., what one fact tells us about another). If the prisoner is dead, does that mean the court order was given?" (Pearl, p. 40)

#### Querying the Bayesian Network&#x20;

* To answer this question in BayesiaLab, you set a Hard Positive Evidence on Death=True (double-click on the state True) to indicate that you learned that the prisoner had been executed (first rung of the ladder).

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692033853/FiringSquad1_mlzgb6.svg" alt=""><figcaption></figcaption></figure>

* In the WebSimulator, you move the slider Death=True to 100%. The Observed Box is automatically checked upon releasing the mouse button, and the evidence is propagated in the network to update the probability distributions of the other variables.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692035597/WebSimulatorDeathTrue_g5jyjb.gif" alt=""><figcaption></figcaption></figure>

Once we know that the prisoner is dead, we infer that both soldiers fired and that the court order was given.&#x20;

### Question #2&#x20;

> "Suppose we find out that A fired. What does that tell us about B? By following the arrows, the computer concludes that B must have fired too. (A would not have fired if the captain hadn’t signaled, so B must have fired as well.) This is true even though A does not cause B (there is no arrow from A to B)." (Pearl, p. 40)

#### Querying the Bayesian Network&#x20;

* This is another observational query, the "first rung of the ladder."
* In BayesiaLab, you set a Hard Positive Evidence on Soldier A=True (double-click on the state True) to indicate that you found out that Soldier A fired.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692034097/FiringSquad2_vlpow5.svg" alt=""><figcaption></figcaption></figure>

* In the WebSimulator, you move the slider Soldier A=True to 100%.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692035630/WebSimulatorSoldierATrue_ogouj0.gif" alt=""><figcaption></figcaption></figure>

Given that we know that Soldier A fired, we infer that the court order was given and that Soldier B also fired.

### Question #3&#x20;

> "Going up the Ladder of Causation, we can ask questions about intervention. What if Soldier A decides on his own initiative to fire, without waiting for the captain’s command? Will the prisoner be dead or alive?" (Pearl, p. 40)&#x20;

#### Querying the Bayesian Network&#x20;

* You can answer this causal question in BayesiaLab by setting Soldier A to Intervention Mode (Monitor Context Menu > Intervention) and then setting Soldier A=True.
* This triggers the "mutilation of the graph" (or "graph surgery"), which blocks the associational path between Soldier A and Death that goes via Captain.
* Alternatively, instead of setting Soldier A to Intervention Mode, you can hold constant the probability distribution of Captain to block the path: Monitor Context Menu > Fix Probabilities.
* Then, you set Hard Evidence on Soldier A=True.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692034231/FiringSquad3_z09d1m.svg" alt=""><figcaption></figcaption></figure>

* In the WebSimulator, you can simulate this intervention by first controlling for Court Order, i.e., checking the box Observed, and then setting Soldier A=True to 100%.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Firing-Squad/WebSimulatorSoldierAIntervention.gif" alt=""><figcaption></figcaption></figure>

If Soldier A decides to fire on his own initiative, this implies the death of the prisoner without affecting our belief regarding the other variables.\
