# Uncertainty, Entropy, and Mutual Information

Now that we have the Ames dataset represented internally in BayesiaLab, we need to become familiar with how BayesiaLab can quantify the probabilistic properties of these nodes and their relationships.

In traditional statistical analysis, we would presumably examine correlation and covariance between the variables to establish their relative importance, especially regarding the target variable Sale Price. In this chapter, we take an alternative approach based on information theory. Instead of computing the correlation coefficient, we consider how the uncertainty of the states of a to-be-predicted variable is affected by observing a predictor variable.

Beyond our common-sense understanding of uncertainty, there is a more formal quantification of uncertainty in information theory: [Entropy](../../key-concepts/entropy/). More specifically, we use [Entropy](../../key-concepts/entropy/) to quantify the uncertainty manifested in the probability distribution of a variable or of a set of variables. In the context of our example, the uncertainty relates to the to-be-predicted home price.

It is fair to say that we would need detailed information about a property to predict its value reasonably. However, in the absence of any specific information, would we be entirely uncertain about its value? Probably not. Even if we did not know anything about a particular house, we would have some contextual knowledge, i.e., that the house is in Ames, Iowa, rather than in midtown-Manhattan, and that the property is a private home rather than a shopping mall. That knowledge significantly reduces the range of possible values. True uncertainty would mean that a value of $0.01 is as probable as a value of $1 million or $1 billion. That is clearly not the case here. So, how uncertain are we about the value of a random home in Ames prior to learning anything about that particular home? The answer is that we can compute the entropy from the marginal probability distribution of home values in Ames. Since we have the Ames dataset already imported into BayesiaLab, we can display a histogram of SalePrice by bringing up its Monitor.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/MonitorSalePriceMarginal.svg)\


This Monitor reflects the discretization intervals that we defined during the data import. It is now easy to see the frequency of prices in each price interval, i.e., the marginal distribution of SalePrice. For instance, only about 2% of homes sold had a price of $75,000 or less. On the basis of this probability distribution, we can now compute the [Entropy](../../key-concepts/entropy/). The definition of [Entropy](../../key-concepts/entropy/) for a discrete distribution is:

$$H(X) = - \sum\limits_{x \in X} {P(x){{\log }_2}P(x)}$$

Entering the values displayed in the Monitor, we obtain:

$$H(SalePrice) = - (0.0208 \times {\log _2}(0.0208) + 0.413 \times {\log _2}(0.413) + 0.3539 \times {\log _2}(0.3539) + 0.1338 \times {\log _2}(0.1338) + 0.0785 \times {\log _2}(0.0785)) = 1.85$$

In information theory, the unit of information is "bit", which is why we use base 2 of the logarithm. On its own, the calculated [Entropy](../../key-concepts/entropy/) value of 1.85 bits may not be a meaningful measure. To understand how much or how little uncertainty this value represents, we compare it to two easily-interpretable measures, i.e., “no uncertainty” and “complete uncertainty.”

No uncertainty means that the probability of one bin (or state) of SalePrice is 100%. This could be, for instance, P(SalePrice<=75000)=1.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/MonitorSalePrice75000.svg)

We now compute the entropy of this distribution once again:

$$H(SalePric{e_{ < 75,000}}) =  - (1 \times {\log _2}(1) + 0 \times {\log _2}(0) + 0 \times {\log _2}(0) + 0 \times {\log _2}(0) = {\log _2}(1) = 0$$

Here,

$$0 \times {\log _2}(0)$$

is taken as 0, given the limit

$$\mathop {\lim }\limits_{p \to 0 + } p{\log _2}(p) = 0$$

This means that “no uncertainty” has zero Entropy.

What about the opposite end of the spectrum, i.e., complete uncertainty? Maximum uncertainty exists when all possible states of a distribution are equally probable when we have a uniform distribution:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/MonitorSalePriceUniform.svg)

Once again, we calculate the entropy:

$$H(SalePric{e_{uniform}}) =  - (0.2 \times {\log _2}(0.2) + 0.2 \times {\log _2}(0.2) + 0.2 \times {\log _2}(0.2) + 0.2 \times {\log _2}(0.2) + 0.2 \times {\log _2}(0.2) = {\log _2}(5) = 2.3219$$

The value 5 in the logarithm of the simplified equation reflects the number of states. This means that the [Entropy](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/key-concepts-entropy) is a function of the variable discretization. In addition to the previously computed Marginal Entropy of 1.85, we now have the values 0 and 2.3219 for “no uncertainty” and “complete uncertainty,” respectively.

### Entropy and Predictive Importance&#x20;

How do such entropy values help us to establish the importance of predictive variables? If there is no uncertainty regarding a variable, one state of this variable has to have a 100% probability, and predicting that particular state must be correct. This would be like predicting the presence of clouds during rain. On the other hand, if the probability distribution of the target variable is uniform, e.g., the outcome of a fair coin toss, a random prediction has to be correct with a probability of 50%.

In the context of house prices, knowing the marginal distribution of SalePrice and assuming this distribution is still true when we make the prediction, predicting SalePrice>=150000 would have a 41.28% probability of being correct, even if we knew nothing else. However, we would expect that observing an attribute of a specific home would reduce our uncertainty concerning its SalePrice and increase our probability of making a correct prediction for this particular home. In other words, conditional upon learning an attribute of a home, i.e., by observing a predictive variable, we expect a lower uncertainty for the target variable, SalePrice.

For instance, the moment we learn of a particular home that LotArea=200,000 (measured in square feet. 200,000 ft2 ≈ 4.6 acres ≈ 18,851 m2 ≈ 1.86 ha), and assuming, again, that the estimated marginal distribution is still true when we are making the prediction, we can be certain that SalePrice>300000. This means that upon learning the value of this home’s LotArea, the entropy of SalePrice goes from 1.85 to 0. Learning the size reduces our entropy by 1.85 bits. Alternatively, we can say that we gain information amounting to 1.85 bits.

The information gain or entropy reduction from learning about LotArea of this house is obvious. Observing a different home with a more common lot size, e.g., LotArea=10,000, would presumably provide less information and, thus, have less predictive value for that home.

However, we wish to know how much information we would gain on average—considering all values of LotArea along with their probabilities—by generally observing it as a predictive variable for SalePrice. Knowing this “average information gain” would reflect the predictive importance of observing the variable LotArea.

To compute this, we need two quantities. First, the marginal entropy of the target variable H(SalePrice), and second, the conditional entropy of the target variable given the predictive variable:

$$H(SalePrice|LotArea) = \sum\limits_i {P(} SalePric{e_i})H(SalePric{e_i}|LotAre{a_i})$$

The difference between the marginal entropy of the target variable and the conditional entropy of the target given the predictive variable is formally known as [Mutual Information](../../key-concepts/mutual-information/), denoted by I. In our example, the [Mutual Information](../../key-concepts/mutual-information/) I between SalePrice and LotArea is the marginal entropy of SalePrice minus the conditional entropy of SalePrice given LotArea:

$$I(SalePrice,LotArea) = H(SalePrice) - H(SalePrice|LotArea)$$

More generally, the [Mutual Information](../../key-concepts/mutual-information/)  I between variables X and Y is defined by:

$$I(X,Y) = H(X) - H(X|Y)$$

which is equivalent to:

$$I(X,Y) = \sum\limits_{x \in X} {\sum\limits_{y \in Y} {p(x,y){{\log }_2}} } {{p(x,y)} \over {p(x)p(y)}}$$

and furthermore also equivalent to:

$$I(X,Y) = \sum\limits_{y \in Y} {p(y)\sum\limits_{x \in X} {p(x|y){{\log }_2}} } {{p(x|y)} \over {p(x)}}$$

This allows us to compute the [Mutual Information](../../key-concepts/mutual-information/) between a target variable and any possible predictors. As a result, we can find out which predictor provides the maximum information gain and, thus, has the greatest predictive importance.
