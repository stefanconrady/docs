# Entropy

### Definition&#x20;

Entropy, denoted $$H(X)$$, is a key metric in BayesiaLab for measuring the uncertainty associated with the probability distribution of a variable $${X}$$.

Entropy is expressed in bits and defined as follows:

$$H(X) = - \sum\limits_{x \in X} {p(x){{\log }_2}\left( {p(x)} \right)}$$

The Entropy of a variable $${X}$$ can also be understood as the sum of the Expected Log-Losses of its states.&#x20;

### Example&#x20;

Let's assume we have four containers, A through D, which are filled with balls that can be either blue or red.

* Container A is filled exclusively with blue balls.
* Container B has an equal amount of red and blue balls.
* In Container C, 10.89% of all balls are blue, and the remainder is red.
* Container D only holds red balls.
* Within each container, the order of balls is entirely random.
* A volunteer who already knows the proportions of red and blue balls in each container now randomly draws one ball from each container. What is his degree of uncertainty regarding the ball color at the moment of each draw?
* Needless to say, with Containers A and D, there is no uncertainty at all. From Containers A and D, he will draw a blue and red ball, respectively, with perfect certainty. What about the degree of certainty or, rather, uncertainty for Containers B and C?
* The concept of Entropy can formally represent the degree of uncertainty.
* We use the binary variable $${X}$$ to represent the color of the ball.
* Using the definition of Entropy from above, we can compute the Entropy value applicable to each draw.

<table data-full-width="true"><thead><tr><th>Container A</th><th>Container B</th><th>Container C</th><th>Container D</th></tr></thead><tbody><tr><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/BlueRed100-0.svg" alt=""></td><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/BlueRed50-50.svg" alt=""></td><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/BlueRed11-89.svg" alt=""></td><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/BlueRed0-100.svg" alt=""></td></tr><tr><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/BlueBalls300x169.png" alt=""></td><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/BlueBalls50pct_300x169.png" alt=""></td><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/BlueBalls10pct_300x169.png" alt=""></td><td><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Entropy/RedBalls300x169.png" alt=""></td></tr></tbody></table>

We can also plot Entropy as a function of the probability of drawing a red ball.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1710350875/Entropy_ndhdxd.svg" alt=""><figcaption></figcaption></figure>

We see that Entropy reaches its maximum value for $$P\left( {X = red} \right) = P\left( {X = blue} \right) = 0.5$$, i.e., when drawing a red or a blue ball is equally probable. A 50/50 mix of red and blue balls is indeed the situation with the highest possible degree of uncertainty.

### Maximum Entropy as a Function of the Number of States&#x20;

This was an example of a variable with two states only. As we introduce more possible states, e.g., another ball color, the maximum possible Entropy increases.

More specifically, the maximum value of Entropy increases logarithmically with the number of states $${S}$$ of node $${X}$$.

$${H_{\max }}(X) = {\log _2}({S_X})$$

where $${S_X}$$ is the number of states of the variable $${X}$$.

As a result, one cannot compare the Entropy values of variables with different numbers of states.

To make Entropy comparable, the [Normalized Entropy](normalized-entropy.md) metric is available, which takes into account the Maximum Entropy.
