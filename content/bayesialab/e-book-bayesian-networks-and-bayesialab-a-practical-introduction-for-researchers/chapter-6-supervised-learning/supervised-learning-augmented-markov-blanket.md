# Supervised Learning: Augmented Markov Blanket

### Augmented Markov Blanket&#x20;

Given the performance of the Markov Blanket algorithm in the previous section ([Supervised Learning: Markov Blanket](supervised-learning-markov-blanket.md)), we are now looking for improvements by considering alternatives within the group of Supervised Learning algorithms.

BayesiaLab offers an extension to the Markov Blanket algorithm, namely the Augmented Markov Blanket, which performs an Unsupervised Learning algorithm on the nodes in the Markov Blanket. This relaxes the constraint of requiring orthogonal child nodes. Thus, it helps identify any influence paths between the predictor variables and potentially improves the predictive performance. Adding such arcs would be similar to automatically creating interaction terms in a regression analysis.

After returning to the [Modeling Mode](../../user-guide/main-menu/view/modeling-mode.md) (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1690829528/F4\_hiym4a.svg) or ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184233/BayesiaLab\_Icons/Modeling-Mode-Icon\_s6tz0u.svg)) we start this learning algorithm via `Main Menu > Learning > Supervised Learning > Augmented Markov Blanket`.

Note that we are using the original Learning/Test Sets split again. The ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184173/BayesiaLab\_Icons/database-type\_m5kkjw.svg) symbol tagged onto the database icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184169/BayesiaLab\_Icons/database\_uxupjf.svg) reminds us that the Learning Set and Test Set split is in place.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/SupervisedLearningAugmentedMarkovBlanket.png" alt=""><figcaption></figcaption></figure>

As expected, the resulting network is slightly more complex than the Markov Blanket.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AugmentedMarkovBlanket.png" alt=""><figcaption></figcaption></figure>

### Structure Comparison&#x20;

BayesiaLab offers a tool for formally comparing network structures, which we can apply to the Augmented Markov Blanket we just learned and the previously learned Markov Blanket.

We can use `Main Menu > Tools > Compare > Structure` to highlight the differences between both networks.

Given that the addition of two arcs is immediately visible, this function may appear overkill for our example. However, in more complex situations, Structure Comparison can be rather helpful.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/ToolsCompareStructure.png" alt=""><figcaption></figcaption></figure>

By default, the current network appears as the Reference Network, and for the Comparison Network, we select the previously learned Markov Blanket.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/ToolsCompareStructureSelect.png" alt=""><figcaption></figcaption></figure>

Clicking Compare brings up the Structure Comparison Report.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/StructureComparisonReport.png" alt=""><figcaption></figcaption></figure>

This report provides a list of arcs common to both networks and another list of those removed in the Comparison Network.

Clicking Structure Comparison shows a Synthesis Structure that visualizes these differences.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/StructureComparisonSynthesisStructure.png" alt=""><figcaption></figcaption></figure>

The arcs that exist in the Reference Structure, i.e., Augmented Markov Blanket, but do not exist in the Comparison Structure, i.e., the Markov Blanket, are highlighted in red.

Please see Direct Structural Network Comparison for a much more detailed explanation of this tool.

### Performance Analysis

Given that the Augmented Markov Blanket algorithm has only added a single additional arc to the network, compared to what the Markov Blanket algorithm produced, we may not expect a dramatic difference in predictive performance.

However, any improvements in terms of reducing the False Negative would be welcome. So, we run the Network Performance Analysis again: `Main Menu > Analysis > Network Performance > Target`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/NetworkPerformanceTargetAMB.png" alt=""><figcaption></figcaption></figure>

As the analysis starts, BayesiaLab prompts us to specify the Target Evaluation Setting. Again, we select Evaluate All States and proceed.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/TargetEvaluationSettings.png" alt=""><figcaption></figcaption></figure>

Using the previously defined Test Set for evaluating our model, we obtain the performance report:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/TargetEvaluationWindowAMB.png" alt=""><figcaption></figcaption></figure>

Now, we can compare the new performance metrics of the Augmented Markov Blanket with the ones previously obtained with the Markov Blanket.

### Evaluation Against Test Set

| Markov Blanket                                                                                                                                           | Augmented Markov Blanket                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Overall Precision: 90.224%                                                                                                                               | Overall Precision: 94.669%                                                                                                                                |
| False Negative Rate: 15%                                                                                                                                 | False Negative Rate: 2.5%                                                                                                                                 |
| <p><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/ConfusionMatrixMB.svg" alt=""><br></p> | <p><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/ConfusionMatrixAMB.svg" alt=""><br></p> |

Most notable is the change in False Negatives, which drops from 5 to 1, i.e.,  a reduction from 15% to 2.5% in the False Negative Rate.

If this performance were to hold, it could turn this model from moderately useful to a valuable diagnostic tool.

### Cross-Validation&#x20;

Recognizing the potential of the Augmented Markov Blanket algorithm, we proceed to the K-Folds Cross-Validation: `Main Menu > Tools > Cross-Validation > Targeted Evaluation > K-Fold`.

The steps are identical to what we did for the Markov Blanket, so we move straight to the report.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/CrossValidationReportAugmentedMarkovBlanket.png)

As it turns out, the Cross-Validation Report does not confirm the excellent False Negative Rate that the evaluation with regard to the Test Set suggested.&#x20;

Nevertheless, comparing the Cross-Validation results, the Augmented Markov Blanket algorithm delivers an improvement over the Markov Blanket.

### Cross-Validation Result Synthesis

| Markov Blanket                                                                                                                                                          | Augmented Markov Blanket                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Overall Precision: 92.97%                                                                                                                                               | Overall Precision: 94.2%                                                                                                                                                 |
| False Negative Rate: 11.32%                                                                                                                                             | False Negative Rate: 9.43%                                                                                                                                               |
| <p><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/CrossValidationPrecisionMatrixMB.svg" alt=""><br></p> | <p><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/CrossValidationPrecisionMatrixAMB.svg" alt=""><br></p> |

With the apparent advantage of the Augmented Markov Blanket model, we will now try to fine-tune this model further in pursuit of a performance gain.&#x20;

In the next section, [Structural Coefficient Analysis](supervised-learning-structural-coefficient-analysis.md), we explore how adjusting the Structural Coefficient can bring us closer to the performance limits of the model.
