# Game 1

### Game 1 in BayesiaLab

The causal Bayesian network for Game 1 is available for download here:​

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_BackDoor1.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692041053/BoW\_BackDoor1\_lixeei.xbl)

* In the spirit of games, we took advantage of BayesiaLab's ability to embellish nodes and added "start" and "finish" icons for the variables X and Y, respectively.
*   In each game, you need to determine the set of variables you need to adjust for (if any), to estimate the causal effect of X (Start) on Y (Finish) without bias.\
    \


    <figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692040892/BD_Game1_dfoztr.svg" alt="" width="375"><figcaption></figcaption></figure>
* As with all networks presented here, we will reason purely based on the causal structure and do not need to consider parameters or numerical values.
* For demonstration purposes, the Bayesian networks you can download do contain states and numerical values. However, we chose them arbitrarily, and you should feel free to replace them with any other values of your choice. As long as you maintain the causal structure, the content of the nodes, e.g., numerical or categorical, does not matter at all.
* BayesiaLab offers the Influence Paths to Target function, which highlights causal and noncausal paths in a network.
* This feature analyzes the paths from the selected node X to the Target Node Y.
* To start the function, select `Main Menu > Analysis > Visual > Graph > Influence Paths to Target`.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692040984/BackDoorCriterionGame1_u8gqrq.mp4" %}

* This analysis highlights causal paths in blue and noncausal paths in pink.
* However, no pink paths appear, which means that no noncausal paths exist from X to Y.&#x20;
* As a result, no noncausal paths need to be blocked, and, therefore, we do not need to control for any variables to estimate the causal effect of X on Y. The association between X and Y corresponds to the causal effect.
