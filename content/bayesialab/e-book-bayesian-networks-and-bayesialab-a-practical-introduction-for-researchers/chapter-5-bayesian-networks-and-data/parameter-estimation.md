# Parameter Estimation

Now we can see the real benefit of bringing all variables as nodes into BayesiaLab. To calculate [Mutual Information](../../key-concepts/mutual-information/), all the terms of the equation $$I(X,Y)=H(X)-H(X|Y)$$ can be easily computed with BayesiaLab once we have a fully specified network.

We start with a pair of nodes, namely Neighborhood and SalePrice. As opposed to LotArea, which is a discretized Continuous variable, Neighborhood is categorical, and, as such, it has been automatically treated as Discrete in BayesiaLab. This is the reason the node corresponding to Neighborhood has a solid border. We now add an arc between these two nodes to explicitly represent the dependency between them:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/BayesiaLabAmes1.png" alt=""><figcaption></figcaption></figure>

The yellow warning triangle ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184064/BayesiaLab\_Icons/warning-icon\_plawf9.svg) reminds us that the Conditional Probability Table (CPT) of SalePrice given Neighborhood has not been defined yet. In [Chapter 4](../chapter-4-knowledge-modeling-and-probabilistic-reasoning.md), we defined the CPT based on existing knowledge. On the other hand, as we have an associated database, BayesiaLab can use it to estimate the CPT by using [Maximum Likelihood](../../key-concepts/maximum-likelihood-estimation/), i.e., BayesiaLab “counts” the (co-)occurrences of the states of the variables in our data. The table below shows the first 10 records of the variables SalePrice and Neighborhood from the Ames dataset.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689981692/NeighborhoodMarginalDistribution2_gmqh3n.svg" alt="" width="563"><figcaption></figcaption></figure>

Counting all records, we obtain the marginal count of each state of Neighborhood.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689981910/CountOfNeighborhood_ebqlwx.svg" alt=""><figcaption></figcaption></figure>

Given that our Bayesian network structure says that Neighborhood is the parent node of SalePrice, we now count the states of SalePrice conditional on Neighborhood. This is simply a cross-tabulation.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689982220/SalesPriceDistributionByNeighborhood_zos51h.svg" alt=""><figcaption></figcaption></figure>

Once we translate these counts into probabilities (by normalizing by the total number of occurrences for each row in the table), this table becomes a CPT. Together, the network structure (qualitative) and the CPTs (quantitative) comprise the Bayesian network.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689982839/PriceConditionalOnNeighborhood_vzrovl.svg" alt=""><figcaption></figcaption></figure>

In practice, however, we do not need to bother with these individual steps. Rather, BayesiaLab can automatically learn all marginal and conditional probabilities from the associated database. We select `Main Menu > Learning > Parameter Estimation` to perform this task.

Upon completing the Parameter Estimation, the warning triangle ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184064/BayesiaLab\_Icons/warning-icon\_plawf9.svg) has disappeared, and we can verify the results by double-clicking SalePrice to open the Node Editor. Under the tab `Probability Distribution > Probabilistic` we can see the probabilities of the states of SalePrice given Neighborhood. The CPT presented in the Node Editor is indeed identical to the table shown above.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/AmesNodeEditorProbabilityDistributionProbabilistic.png" alt=""><figcaption></figcaption></figure>

This model now provides the basis for computing the [Mutual Information](../../key-concepts/mutual-information/) between Neighborhood and SalePrice. BayesiaLab computes Mutual Information on demand and can display its value in numerous ways. For instance, in [Validation Mode](../../user-guide/main-menu/view/validation-mode.md) (F5), we can select `Main Menu > Analysis > Visual > Arc > Overall > Mutual Information`. &#x20;

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/AmesAnalysisVisualOverallArcMutualInformation.png" alt=""><figcaption></figcaption></figure>

The value of [Mutual Information](../../key-concepts/mutual-information/) is now represented graphically in the thickness of the arc. This does not give us much insight because we only have a single arc in this network. So, we click the Show Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) in the Toolbar to show the numerical values.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/AmesShowArcMutualInformation.png" alt=""><figcaption></figcaption></figure>

The top number in the Arc Comment box shows the actual [Mutual Information](../../key-concepts/mutual-information/) value, i.e., 0.6462 bits. We should also point out that Mutual Information is a symmetric measure. As such, the amount of Mutual Information that Neighborhood provides on SalePrice is the same as the amount of MI that SalePrice provides with regard to Neighborhood. This means that knowing the SalePrice reduces the uncertainty with regard to Neighborhood, even though that may not be of interest.

<img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/MutualInformationArcComment.svg" alt="" data-size="original">

Without context, however, the value of Mutual Information is not meaningful. Hence, BayesiaLab provides an additional measure, i.e., the [Symmetric Normalized Mutual Information](../../key-concepts/mutual-information/symmetric-normalized-mutual-information.md). which gives us a sense of how much the entropy of SalePrice was reduced. Previously, we computed the marginal entropy of SalePrice to be 1.85. Dividing the [Mutual Information](../../key-concepts/mutual-information/) by the Marginal Entropy of SalePrice gives us a sense of how much our uncertainty is reduced:

$${{0.5999} \over {1.85}} = 0.3243 = 32.43\%$$

Conversely, the red number shows the [Relative Mutual Information](../../key-concepts/mutual-information/relative-mutual-information.md) with regard to the parent node, Neighborhood. Here, we divide the [Mutual Information](../../key-concepts/mutual-information/), which is the same in both directions, by the Marginal Entropy of Neighborhood:

$${{0.5999} \over {4.1839}} = 0.1434 = 14.34\%$$

This means that by knowing Neighborhood, we reduce our uncertainty regarding SalePrice by 32% on average. By knowing SalePrice, we reduce our uncertainty regarding Neighborhood by 14% on average. These values are readily interpretable. However, we need to know this for all nodes to determine which node is most important.
