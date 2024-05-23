# Teahouse

### The Teahouse Example&#x20;

> "To see how Bayes’s method works, let’s start with a simple example about customers in a teahouse, for whom we have data documenting their preferences. Data, as we know from Chapter 1, are totally oblivious to cause-effect asymmetries and hence should offer us a way to resolve the inverse-probability puzzle."
>
> [Pearl, Judea. The Book of Why: The New Science of Cause and Effect (pp. 99-100). Basic Books. Kindle Edition.](https://amzn.to/322imYl)

### Will you have a scone with your tea?&#x20;

* To reason about this domain, we first import a small CSV file, which represents Table 3.1 from the book, into BayesiaLab.\
  ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109035/csv\_v1imah.svg) [Tea-Scones.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692035885/Tea-Scones\_jpylgm.csv)
* Upon completing the data import, the two variables, Tea and Scones, are represented as nodes.
* Now we manually add an arc from Tea to Scones to represent a relationship between the nodes.
* Then, we let BayesiaLab estimate the probabilities of this relationship using Maximum Likelihood Estimation: `Main Menu > Learning > Parameter Estimation`.
* The resulting Bayesian network is available in XBL format here:\
  ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) [Teahouse.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692035964/Teahouse\_hlkp99.xbl)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036573/TeaHouse_nzcewr.svg" alt=""><figcaption></figcaption></figure>

* Note that the arc between Tea and Scones does not have any causal meaning here. It merely represents the association between Tea and Scones.
* As a result, we could invert the arc without changing the representation of this non-causal example.
* You can experiment with this model in BayesiaLab or via this WebSimulator page: [https://simulator.bayesialab.com/#!simulator/160655093718](https://simulator.bayesialab.com/#!simulator/160655093718)
* The following screen capture from the WebSimulator illustrates that the proportion of customers who ordered both tea and scones is indeed 1/3, i.e., the Joint Probability equals 1/3, as shown in the Output Panel on the right.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692037246/Teahouse_hlkp99.xbl.gif" alt=""><figcaption></figcaption></figure>

### The Inverse Probability Problem&#x20;

> "... let $$P(T)$$denote the probability that a customer orders tea and $$P(S)$$ denote the probability he orders scones. If we already know a customer has ordered tea, then $$P(S | T)$$ denotes the probability that he orders scones. (Remember that the vertical line stands for “given that.”) Likewise, $$P(T | S)$$ denotes the probability that he orders tea, given that we already know he ordered scones ...
>
> $$P(S | T) P(T) = P(T | S) P(S)$$
>
> This innocent-looking equation came to be known as “Bayes’s rule.” If we look carefully at what it says, we find that it offers a general solution to the inverse-probability problem." (Pearl, p. 101)

### Will you have tea with your scone?&#x20;

* To answer this question, we need to perform probabilistic inference with the WebSimulator by setting Scones to Yes.
* Then, the WebSimulator automatically infers the probability of Tea=Yes, which is now 80%.
* The Joint Probability of 41.67% corresponds to the Marginal Likelihood $$P(T)$$, i.e., the prior probability of a customer ordering a scone.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692037289/TeahouseSconeYes_awjwoh.gif" alt=""><figcaption></figcaption></figure>

### Updating Beliefs in Response to Evidence&#x20;

> "We can also look at Bayes’s rule as a way to update our belief in a particular hypothesis. This is extremely important to understand because a large part of human belief about future events rests on the frequency with which they or similar events have occurred in the past. \[...]
>
> As we saw, Bayes’s rule is formally an elementary consequence of his definition of conditional probability. But epistemologically, it is far from elementary. It acts, in fact, as a normative rule for updating beliefs in response to evidence. In other words, we should view Bayes’s rule not just as a convenient definition of the new concept of “conditional probability” but as an empirical claim to faithfully represent the English expression “given that I know.” (Pearl, pp. 101-102)&#x20;
