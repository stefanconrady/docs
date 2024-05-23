# The Monty Hall Problem

### Context&#x20;

> “Suppose you’re on a game show, and you’re given the choice of three doors. Behind one door is a car, behind the others, goats. You pick a door, say #1, and the host, who knows what’s behind the doors, opens another door, say #3, which has a goat. He says to you, ‘Do you want to pick door #2?’ Is it to your advantage to switch your choice of doors?”
>
> Pearl, Judea. The Book of Why: The New Science of Cause and Effect (p. 190). Basic Books. Kindle Edition.

The problem that Judea Pearl describes is based on the popular game show, [Let's Make a Deal](https://en.wikipedia.org/wiki/Let's\_Make\_a\_Deal). The show, launched in 1963, was hosted for nearly 30 years by [Monty Hall](https://en.wikipedia.org/wiki/Monty\_Hall). Given its counterintuitive (and controversial) solution, the stated problem has been debated extensively in academia and popular science and became widely known as the "[Monty Hall Problem](https://en.wikipedia.org/wiki/Monty\_Hall\_problem)."

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Monty-Hall/LetsMakeADeal-2.jpg" alt="" width="563"><figcaption></figcaption></figure>

### The Game as a Causal Bayesian Network&#x20;

We implemented the Monty Hall Problem as a Causal Bayesian Network in which arcs represent causal relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692057990/MontyHall_rfqsou.svg" alt=""><figcaption></figcaption></figure>

The game can be described with three nodes, and each one of them with three states: Door #1, Door #2, Door #3.

*   Your Door, which represents the initial choice that you make as the contestant in this game. We assume a uniform prior distribution, i.e., each door has the same probability of being picked by you.\


    <figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Monty-Hall/Doors.svg" alt=""><figcaption></figcaption></figure>
* Location of Car, as the name implies, refers to the door behind which the car is hidden. We also assume a uniform prior distribution, i.e., you do not have any knowledge as to where the prize might be located.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Monty-Hall/Doors.svg" alt=""><figcaption></figcaption></figure>

* Door Opened is the door that Monty Hall, the game host, opens. He chooses the door according to the following two rules:
  * He won't open the door that you just selected;
  * He also knows where the car is, so he won't open the door behind which the car is located.
* We represent these two rules in the following Conditional Probability Table:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692057245/MontyHallCPT_cg0igr.svg" alt="" width="563"><figcaption></figcaption></figure>

* We can interpret the first row of this Conditional Probability Table as "If you choose Door #1 and the car is behind Door #1, then Monty Hall will open either Door #2 or Door #3."
* The second row reads: "If you choose Door #1 and the car is behind Door #2, then Monty Hall can only open Door #3."
* Analogously for the third row, "If you choose Door #1 and the car is behind Door #3, then Monty Hall can only open ."
* You can download this Bayesian network in XBL format here:\
  [![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_MontyHall.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692051092/BoW\_MontyHall\_laazm9.xbl)
* Alternatively, you can experiment with different game scenarios via our WebSimulator: [https://simulator.bayesialab.com/#!simulator/137248128314](https://simulator.bayesialab.com/#!simulator/137248128314)

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Monty-Hall/MontyHallWebSimulator.png)

### What's the Optimal Decision?&#x20;

If you experiment with this network in BayesiaLab or the WebSimulator, you will quickly discover that the optimal policy is always to change your door choice.

Let's go through this step by step and try it out in BayesiaLab or the WebSimulator:

* You choose Door #1 and set evidence accordingly on the corresponding node: Your Door=Door #1
* As per the game rules, Monty Hall cannot open Door #1, which you just picked.
* As a result, Monty Hall could only open Door #2 or Door #3.
* However, behind one of the two doors is the car, and Monty Hall knows where the car is.
* As per the game rules, he won't reveal the car and, therefore, must open a door that presents a goat.
* We simulate that Monty Hall opens Door #2 and set the evidence Door Opened=Door #2.&#x20;
* With Door #2 having revealed a goat, the car can only hide behind Door #1 or Door #3.
* Given these pieces of evidence set so far, the Bayesian network updates the distribution of the node Location of Car:
  * Door #1 remains at 1/3.
  * Door #3 increases from 1/3 to 2/3.
* This means that the grand prize, the car, is twice as likely to be behind Door #3 compared to Door #1.
* As a result, you should indeed revise your original door selection and pick the other closed door instead.

### Workflow Animation

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692051269/MontyHallProblem_fqnosq.mp4" %}

{% hint style="warning" %}
The optimal decision policy could be different if we also considered the psychological cost of regret and the expected utility from the prizes.
{% endhint %}

### A Mind-Reading Game?&#x20;

> "If I should switch no matter what door I originally chose, then it means that the producers somehow read my mind. How else could they position the car so that it is more likely to be behind the door I did not choose?
>
> The key element in resolving this paradox is that we need to take into account not only the data (i.e., the fact that the host opened a particular door) but also the data-generating process—in other words, the rules of the game." (Pearl, pp. 191–192)

### V-Structures&#x20;

The Causal Bayesian Network we encoded above does indeed represent the data-generating process of this domain: Monty Hall decides which door to open based on two criteria, (1) the choice of the contestant and (2) the location of the car.

This particular arrangement of two causes and their common effect is called a V-structure. In such a V-structure, we call the common effect a Collider. In our example, the node Door Opened is such a Collider.

V-structures have important characteristics: parent nodes, which are initially independent, become dependent if we set any pieces of evidence on their common child node, i.e., the Collider or any of the Collider's descendants. In other words, in a V-structure, parent nodes are _marginally independent_ but _conditionally dependent_ given evidence on their descendants.&#x20;

{% hint style="info" %}
Please see Structures Within a DAG in [Chapter 10](../../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-10-causal-effect-identification-and-estimation/) of our book to learn more about the important characteristics of different network structures.
{% endhint %}

Now we know that conditioning on Door Opened allows for information to flow from Your Door to Location of Car, as visualized by the green arrow below:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692051461/IntercausalReasoning_noyr3o.png" alt=""><figcaption></figcaption></figure>

> "It is a bizarre dependence for sure, one of a type that most of us are unaccustomed to. It is a dependence that has no cause." (Pearl, p. 194)

It is precisely the difficulty in understanding this conditional dependency that has made this game so intriguing.

### An Incorrect "Common-Sense" Approach&#x20;

Most casual observers, however, would attempt to reason about this problem the way we illustrate in the following _noncausal_ Bayesian network.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692056181/MontyHallCommonSense_gko5cs.svg" alt="" width="375"><figcaption></figcaption></figure>

In this context, the following Conditional Probability Tables would apply:

* For the node Door Opened: Monty Hall cannot open the door the player chose:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Monty-Hall/CommonSenseCPTDoorOpened.svg" alt="" width="563"><figcaption></figcaption></figure>

* For Location of Car: It cannot be behind the door that Monty Hall opened:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Monty-Hall/CommonSenseCPTCarLocation.svg" alt="" width="563"><figcaption></figcaption></figure>

Now that we have formally encoded such a (mis)understanding of the domain, we can simulate the game again:

We pick Door #1, then Monty Hall opens Door #2.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692056400/MontyHallCommonSenseSimulation_vwxxpp.svg" alt="" width="375"><figcaption></figcaption></figure>

With the given (incorrect) network, we would infer that Door #1 and Door#3 have equal probabilities of containing the car. As a result, there would be no reason to reconsider our initial choice.&#x20;

### Dining Room Experiment&#x20;

The disagreement between the normative choice we explained earlier ([What's the Optimal Decision?](the-monty-hall-problem.md#whats-the-optimal-decision)) and the "common-sense" solution presented just now ([An Incorrect "Common-Sense" Approach](the-monty-hall-problem.md#an-incorrect-common-sense-approach)) has fueled fierce debates and puzzled great minds for decades. With all that has been written about this paradox over the years — and we have used the Monty Hall Problem extensively as an example in our training sessions, we should let the inventor of this puzzle illuminate us. The matter was settled once and for all in 1991 with an experiment at the dining table of Monty Hall's residence in Beverly Hills. New York Times journalist John Tierney shares Monty Hall's perspective on the controversy in his article, [Behind Monty Hall's Doors: Puzzle, Debate and Answer?](https://www.nytimes.com/1991/07/21/us/behind-monty-hall-s-doors-puzzle-debate-and-answer.html)
