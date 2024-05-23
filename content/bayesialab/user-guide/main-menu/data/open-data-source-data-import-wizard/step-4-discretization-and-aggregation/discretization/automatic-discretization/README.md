# Automatic Discretization

### Context

* Automatic Discretization covers numerous discretization algorithms that are part of  [Step 4 — Discretization and Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation) of the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source).
* Except for Manual, all items in the Type menu represent Automatic Discretization algorithms.
* Most of these algorithms can also be accessed via the [Generate a Discretization](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-manual-discretization/a/Generate%20a%20Discretization) function within the [Manual Discretization](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-manual-discretization) screen.

### Usage

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689866404/DataImportWizard-4-AutomaticMethods_bfdsr6.png" alt=""><figcaption></figcaption></figure>

* Selecting a Discretization algorithm applies variable by variable, i.e., you can use a different algorithm for each Continuous variable.
* To select a variable, click on the variable header or anywhere inside the column.
* You can perform the selection and deselection of multiple variables with keystroke combinations commonly used in spreadsheet editing:
  * Ctrl+Click: add a variable to the current selection.
  * Shift+Click: add all variables between the currently selected and the clicked variable to the selection.
  * Ctrl+A: select all variables in the Data panel. However, selecting all variables is not useful here in Step 4, as there are no actions that can apply to all variable types.
  * Shift+End: select all variables from the currently selected variable to the rightmost variable in the table.
  * Shift+Home: select all variables from the currently selected variable to the leftmost variable in the table.
* Click the Select All Continuous button to select all Continuous variables.
  * Note that this action will also select any variables which you have already discretized manually. As a result, you may override your previous choices.
  * Note that Continuous variables already discretized manually are highlighted in soft blue.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689863786/ManualDiscretization2_rlyrrs.svg" alt="" width="563"><figcaption></figcaption></figure>

* If you do not specify an algorithm for a variable that was not manually discretized either, the default Discretization algorithm with its default settings will be used.
* You can set the default Discretization algorithm under Main Menu > Window > Preferences > Discretization.\
  \[+] Show More
* For the following algorithms, a Log Transformation is available as an option:
  * [R2-GenOpt\*](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-r2-genopt-x)
  * [R2-GenOpt](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-r2-genopt)
  * [K-Means](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-k-means)
  * [Density Approximation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-density-approximation)
  * [Normalized Equal Distance](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-normalized-equal-distance)
  * [Equal Distance](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-equal-distance)&#x20;
  * Applying the Log Transformation is useful if you have a high density of values at the bottom end of the variable domain. This "stretches" the scale for small values approaching zero.
  * Note that the Log Transformation is only used temporarily for discretization purposes. Thus, the values of the thresholds and values of the intervals can all be interpreted based on the original scale.&#x20;
* For the following algorithms, the option Isolate Zeros is available:
  * [R2-GenOpt\*](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-r2-genopt-x)
  * [R2-GenOpt](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-r2-genopt)
  * [K-Means](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-k-means)
  * [Normalized Equal Distance](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-normalized-equal-distance)
  * Separating 0 into a separate interval can be useful for zero-inflated distributions so as to clearly separate small values from "absolutely nothing."
* Click Finish to perform the Discretization.
* A progress bar displays the status of the Discretization process:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689866667/DataImportWizard-4-DiscretizationProgressBar_ohtwvx.png" alt=""><figcaption></figcaption></figure>

* If a Filtered Value is defined for a Continuous variable, a new artificial interval with an infinitesimally small width of 10-7 will be added after the intervals defined in this step. This newly-created state will serve as the Filtered State, and "\*", i.e., the asterisk character, will be its State Name.
* At its conclusion, BayesiaLab opens up a Graph Window with all imported variables now represented as nodes.
* Simultaneously, a window pops up that offers you an optional [Import Report](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-import-report), which is [Step 5](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-import-report) of the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source).

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689866755/Discretization-5-ImportReportPrompt_yli3fj.png" alt=""><figcaption></figcaption></figure>

### Automatic Discretization Algorithms in Detail

\
