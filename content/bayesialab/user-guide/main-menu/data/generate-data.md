# Generate Data

### Context

* BayesiaLab offers learning algorithms that allow you to generate a Bayesian network from data.
* However, with a given Bayesian network, BayesiaLab can also generate data.
* For this purpose, BayesiaLab draws samples from the [Joint Probability Distribution](../../../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) encoded by the Bayesian network and saves the obtained samples as observations.

### Usage

* Select `Main Menu > Data > Generate Data`.

It is possible to choose to generate the data as an internal database. We can also indicate the rate of missing values of the base and use the long name of the states if the database is written in a file. It is possible to generate a database with test examples by indicating the wanted percentage.

The states' long name can be saved instead of the states' name. If the user wants to save the continuous values, the numerical values will be created randomly in each interval. If the data are generated in [Validation Mode](../view/validation-mode.md) ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184241/BayesiaLab\_Icons/Validation-Mode-Icon\_ttnspc.svg), then the evidence is considered.&#x20;
