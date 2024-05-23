# Calculating Fit: DL(D|B)

To calculate the description length of the data given the Bayesian network, we utilize the fact that the description length is inversely proportional to the probability of the observed data inferred by the model.

$$\begin{array}{l} DL(D|B) = \sum\limits_{j = 1}^N {DL({e_j}|B)} \\ DL(D|B) = \sum\limits_{j = 1}^N {{{\log }_2}\left( {\frac{1}{{{P_B}({e_j})}}} \right)} \\ DL(D|B) = - \sum\limits_{j = 1}^N {{{\log }_2}\left( {{P_B}({e_j})} \right)} \end{array}$$

where

* $${e_j}$$ is the n-dimensional observation described in row $${j}$$, and&#x20;
* $$PB\left( {{e_j}} \right)$$ is the joint probability of this observation returned by the Bayesian network $$B$$.

The chain rule allows rewriting this equation with:

$$\begin{array}{l} DL(D|B) = - \sum\limits_{j = 1}^N {{{\log }_2}\left( {\prod\limits_{i = 1}^n {{P_B}({x_{ij}}|{\pi _{ij}})} } \right)} \\ DL(D|B) = - \sum\limits_{j = 1}^N {\sum\limits_{i = 1}^n {{{\log }_2}\left( {{P_B}({x_{ij}}|{\pi _{ij}})} \right)} } \end{array}$$
