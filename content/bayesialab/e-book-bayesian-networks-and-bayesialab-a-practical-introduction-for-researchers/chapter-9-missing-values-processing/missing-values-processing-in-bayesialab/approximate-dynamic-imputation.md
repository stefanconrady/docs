# Approximate Dynamic Imputation

As stated earlier, any substantial improvement in the performance of missing values processing comes at a high computational cost. Thus, we recommend an alternative workflow for networks with a large number of nodes and many missing values. The proposed approach combines the efficiency of [Static Imputation](infer-static-imputation.md) with the imputation quality of [Dynamic Imputation](infer-dynamic-imputation.md).

[Static Imputation](infer-static-imputation.md) is efficient for learning because it does not impose any additional computational cost on the learning algorithm. With [Static Imputation](infer-static-imputation.md), missing values are imputed in memory, which makes the imputed dataset equivalent to a fully observed dataset.

Even though, by default, [Static Imputation](infer-static-imputation.md) runs only once at the time of data import, it can be triggered to run again at any time by selecting `Main Menu > Learning > Parameter Estimation`. Whenever Parameter Estimation is run, BayesiaLab computes the probability distributions on the basis of the current model. The missing values are then imputed by drawing from these distributions. If we now alternate structural learning and [Static Imputation](infer-static-imputation.md) repeatedly, we can approximate the behavior of the [Dynamic Imputation](infer-dynamic-imputation.md) method. The speed advantage comes from the fact that values are now only imputed (on demand) at the completion of each full learning cycle instead of being imputed at every single step of the structural learning algorithm.

### Usage <a href="#h2_519852009" id="h2_519852009"></a>

As a best-practice recommendation, we propose the following sequence of steps:

1. In [Step 3 of the Data Import Wizard](../../../user-guide/main-menu/data/open-data-source-data-import-wizard/step-3-data-selection-filtering-and-missing-value-processing.md), we choose Static Imputation (standard or entropy-based). This produces an initial imputation with the fully unconnected network, in which all the variables are independent.
2. We run the Maximum Weight Spanning Tree algorithm to learn the first network structure.
3. Upon completion, we prompt another [Static Imputation](infer-static-imputation.md) by running Parameter Estimation. Given the tree structure of the network, pairwise variable relationships provide the distributions used by the [Static Imputation](infer-static-imputation.md) process.
4. Given the now-improved imputation quality, we start another structural learning algorithm, such as EQ, which may produce a more complex network.
5. The latest, more complex network then serves as the basis for yet another [Static Imputation](infer-static-imputation.md). We repeat steps 4 and 5 until we see the network converge toward a stable structure.
6. With a stable network structure in place, we change the imputation method from [Static Imputation](infer-static-imputation.md) to [Structural EM](infer-structural-em.md) via `Main Menu > Learning > Missing Values Processing > Structural EM`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/9-Missing-Values-Processing/Approximate-Dynamic-Imputation/SwitchToStructuralEM.png" alt=""><figcaption></figcaption></figure>

While this Approximate Dynamic Imputation workflow requires more input and supervision by the researcher, for learning large networks, it can save a substantial amount of time compared to using the all-automatic [Dynamic Imputation](infer-dynamic-imputation.md) or [Structural EM](infer-structural-em.md). Here, “substantial” can mean the difference between minutes and days of learning time.
