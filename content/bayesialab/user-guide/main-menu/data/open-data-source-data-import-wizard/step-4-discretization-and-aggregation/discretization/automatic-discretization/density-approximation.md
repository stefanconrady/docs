# Density Approximation

### Context

* Density Approximation is one of the [Automatic Discretization](./) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](../../) of the [Data Import Wizard](../../../).

### Algorithm Details & Recommendations

* The Density Approximation discretization detects changes in the sign of the derivative of the Probability Density Function (PDF) in order to identify local minima and maxima.
* Between each local minimum and maximum, the algorithm creates a threshold.\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/DataImportWizard-4/DensityApproximation/DensityApproximationPDFThresholds.png" alt=""><figcaption></figcaption></figure>

* Also, the algorithm automatically detects the optimal number of bins, although you can specify the maximum number of bins.
* The minimum size permitted for bins is 1% of the data points.
