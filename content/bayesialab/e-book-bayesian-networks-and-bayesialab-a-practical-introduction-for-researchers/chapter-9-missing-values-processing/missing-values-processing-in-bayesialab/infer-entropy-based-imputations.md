# Infer — Entropy-Based Imputations

Under Infer, we have two additional options, namely Entropy-Based Static Imputation and Entropy-Based Dynamic Imputation. As their names imply, they are based on [Static Imputation](infer-static-imputation.md) and [Dynamic Imputation](infer-dynamic-imputation.md).

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-20\_16-56-08.png)

Whereas the standard (non-entropy-based) approaches randomly choose the sequence in which missing values are imputed within a row of data, the entropy-based methods select the order based on the conditional uncertainty associated with the unobserved variable. More specifically, missing values are imputed first for those variables that meet the following conditions:

1. Variables that have a fully-observed/imputed Markov Blanket;
2. Variables that have the lowest conditional entropy, given the observations and imputed values.

The advantages of the entropy-based methods are (a) the speed improvement over their corresponding standard methods and (b) their improved ability to handle datasets with large proportions of missing values.
