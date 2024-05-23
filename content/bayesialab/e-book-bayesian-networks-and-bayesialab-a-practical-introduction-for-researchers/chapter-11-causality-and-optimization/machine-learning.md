# Machine Learning

The way out of this predicament is to turn to modeling. Instead of working with an enormously large joint probability table, we will approximate the joint probability distribution of the domain with a model. But does this not take us back to the problem of being unable to machine-learn a causal model? No, because we do not need a causal model. Rather, we merely need a statistical model to approximate the statistical relationships of the variables in our domain. Of course, that task is easy. In earlier chapters, we have already introduced various machine learning algorithms in BayesiaLab that can generate Bayesian networks from data.

Given that we have a target variable, i.e., Sales, Supervised Learning will be the appropriate approach. First, we import the dataset [ACME\_Data.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1691095010/ACME\_Data\_qvhdfc.csv) and discretize all variables with the R2GenOpt algorithm into five states. Our choice of this discretization algorithm follows the rationale that we presented in earlier chapters.&#x20;

After importing the dataset, we use the Augmented Naive Bayes algorithm to learn a network with Sales as the Target Node. The result is shown below.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691095196/ANBN_ggziut.svg" alt="" width="375"><figcaption></figcaption></figure>

Here, we will omit a discussion of the network quality. Rather, we proceed with the given network and look at how to use it to understand our problem domain.

As is, this network has the familiar appearance of a predictive model. And we have kept emphasizing that machine learning can only produce predictive models, which, in turn, are only capable of performing observational inference. However, it is causal inference that we require for the purpose of marketing mix optimization. Clearly, a causal interpretation of the arcs in the above network would not make any sense. After all, Sales is the outcome, not the cause.

This does not matter because we had no intention of finding a causal model with machine learning. We had already given up on finding the true causal model. The model we obtained is only meant to compactly represent the [Joint Probability Distribution (JPD)](../../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) of all variables in this domain.

Our key to causal inference is that we have the JPD, as represented by the machine-learned Bayesian network, and we know, based on domain knowledge and the Disjunctive Cause Criterion, which variables are Confounders.

One issue remains open, though, and that is what mechanism to use for estimation. Recall matching as an estimation technique and, in particular, Likelihood Matching (see Intuition for Matching). Here, however, we are not dealing with just one covariate Z, but rather with 10, of which 8 are confounders.

### Confounders and Non-Confounders <a href="#h3_1707165997" id="h3_1707165997"></a>

Before proceeding to estimation in BayesiaLab, we need to formally declare which variables are Confounders. In BayesiaLab, all nodes are considered Confounders by default. Hence, we need to declare the inverse condition, i.e., we must tell BayesiaLab which nodes are _not_ Confounders or “Non-Confounders.”

#### **Designate Non-Confounders**

As per the rationale we laid out earlier, we need to mark the pre-treatment variables Competitive Print, Competitive TV, and Competitive TV and assign them to the predefined Class Non\_Confounders.

* Select the nodes to be added to the Class Non\_Confounders.
* Right-click on one of them to bring up the Contextual Menu.
* Select `Properties > Classes > Add`.
* Check the radio box for Predefined Class and pick Non\_Confounder from the drop-down menu.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083803/AddToClassNonConfounder_yphe3e.mp4" %}

As a result, we now have a clear distinction between Confounders and Non-Confounders and can perform an effect estimation on that basis.

**Add Color to Non-Confounders**

To highlight this distinction, we assign colors to each Class.

* Right-click on the Graph Panel background to bring up the Contextual Menu.
* Select Edit Classes.
* In the Class Editor, highlight Non\_Confounder in the list and click Associate Colors.
* From the dialog box, select Associate Default Colors with Classes and click OK.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083804/AssociateColorWithClasses2_ljfwal.mp4" %}

Now, all Non-Counfounders are highlighted in red.

### Many Confounders, Many Treatments, Many Levels <a href="#h3_347994593" id="h3_347994593"></a>

Under [Estimation Challenges](background-challenges-and-objectives.md#h3\_\_1376158685), we already pointed out that stratification is no longer feasible as an estimation technique, which leaves us with matching. However, this example exceeds in complexity of Simpson’s Paradox in a number of ways. In Simpson’s Paradox, we had one Confounder and one treatment variable, which had only one treatment level.&#x20;

Now we have several Confounders and several treatments. And many of the treatment variables have multiple treatment levels. As a result, the task of matching is no longer straightforward. Now, we need to simultaneously balance all Confounders with regard to each treatment variable in such a way that each treatment remains at its marginal probability level. With that in place, we can simulate different treatment levels and observe the corresponding outcomes. What we then observe in the different outcomes is indeed the causal effect. It is easy to imagine that the computational effort for this process is substantial. It goes beyond the scope of this book to explain the details of BayesiaLab’s Likelihood Matching algorithm. For our purposes, we only need to know how to invoke the algorithm in BayesiaLab for causal effect estimation. Likelihood Matching is launched whenever we run Direct Effects in BayesiaLab.
