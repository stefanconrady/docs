# Where Is My Bag?

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Where-is-my-bag/shutterstock_1036337032_970x245.jpg" alt=""><figcaption></figcaption></figure>

### Context

> "So far I have emphasized only one aspect of Bayesian networks—namely, the diagram and its arrows that preferably point from cause to effect. Indeed, the diagram is like the engine of the Bayesian network. But like any engine, a Bayesian network runs on fuel. The fuel is called a conditional probability table \[...]
>
> Let’s look at a concrete example, suggested by Stefan Conrady and Lionel Jouffe of BayesiaLab, Inc. It’s a scenario familiar to all travelers: we can call it “Where Is My Bag?” Suppose you’ve just landed in Zanzibar after making a tight connection in Aachen, and you’re waiting for your suitcase to appear on the carousel. Other passengers have started to get their bags, but you keep waiting… and waiting… and waiting. What are the chances that your suitcase did not actually make the connection from Aachen to Zanzibar? The answer depends, of course, on how long you have been waiting. If the bags have just started to show up on the carousel, perhaps you should be patient and wait a little bit longer. If you’ve been waiting a long time, then things are looking bad."
>
> [Pearl, Judea. The Book of Why: The New Science of Cause and Effect (pp. 116-118). Basic Books. Kindle Edition.](https://amzn.to/322imYl)

### The Problem Domain as a Bayesian Network&#x20;

* You can find the original and complete description of this example in [Chapter 4 of our book, Bayesian Network & BayesiaLab](../../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-4-knowledge-modeling-and-probabilistic-reasoning.md).
* We encoded the problem domain as a Bayesian network in XBL format, which you can download here:\
  [![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_Bag.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692038675/BoW\_Bag\_mli8xa.xbl)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692038868/WIMB_x8oiqk.svg" alt=""><figcaption></figcaption></figure>

* The [Conditional Probability Table](../../key-concepts/conditional-probability-table-cpt.md) shown below is associated with the node Bag on Carousel and encodes our assumptions regarding the delivery of bags at the airport.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/webinars-seminars-examples/The-Book-of-Why/Where-is-my-bag/BagCPT.png" alt=""><figcaption></figcaption></figure>

### What does this table mean?

> "This table, though large, should be easy to understand. The first eleven rows say that if your bag didn’t make it onto the plane (bag on plane = false) then, no matter how much time has elapsed, it won’t be on the carousel (carousel = false). That is, P(carousel = false | bag on plane = false) is 100 percent. That is the meaning of the 100s in the first eleven rows. The other eleven rows say that the bags are unloaded from the plane at a steady rate. If your bag is indeed on the plane, there is a 10 percent probability it will be unloaded in the first minute, a 10 percent probability in the second minute, and so forth. For example, after 5 minutes there is a 50 percent probability it has been unloaded, so we see a 50 for P(carousel = true | bag on plane = true, time = 5). After ten minutes, all the bags have been unloaded, so P(carousel = true | bag on plane = true, time = 10) is 100 percent. Thus we see a 100 in the last entry of the table." (Pearl, p. 119)

### The Curve of Abandoning Hope

> "The most interesting thing to do with this Bayesian network, as with most Bayesian networks, is to solve the inverse-probability problem: if x minutes have passed and I still haven’t gotten my bag, what is the probability that it was on the plane? Bayes’s rule automates this computation and reveals an interesting pattern. After one minute, there is still a 47 percent chance that it was on the plane. (Remember that our prior assumption was a 50 percent probability.) After five minutes, the probability drops to 33 percent. After ten minutes, of course, it drops to zero." (Pearl, p. 119)

### Querying the Bayesian Network&#x20;

* You can experiment with this model in our WebSimulator: [https://simulator.bayesialab.com/#!simulator/470237376209](https://simulator.bayesialab.com/#!simulator/470237376209) and see how the probabilities evolve as a function of time.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692039102/WhereIsMyBagWebSimulator_uo8u5d.mp4" %}

* In BayesiaLab, you can automatically generate and plot the "Curve of Abandoning Hope."
* First, you need to define Bag on Plane as your Target Node.
* Then set Bag on Carousel=False as Hard Evidence.
* Finally, select `Main Menu > Analysis > Visual > Target > Target's Posterior > Histogram`.
* The x-axis represents Elapsed Time, the y-axis the posterior probability of Bag on Plane=True given Bag on Carousel=False and Elapsed Time.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692039102/WhereIsMyBagBayesiaLabHistogram_xzhhy8.mp4" %}
