# R2-GenOpt

### Context

* R2-GenOpt is one of the [Automatic Discretization](./) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](../../) of the [Data Import Wizard](../../../).

### Algorithm Details & Recommendations

* The R2-GenOpt algorithm utilizes a Genetic Algorithm to find a discretization that maximizes the R2 between the discretized variable and its corresponding (hidden) Continuous variable.
* As such, it is the optimal approach for achieving the first objective of discretization, i.e., finding a precise representation of the values of a Continuous variable.
* This algorithm takes into account the Minimum Interval Weight and can also create a specific bin for representing zeros if the Isolate Zeros option is set.
* In Validation Mode, the R2 value between the Discretized variable and its corresponding Continuous variable can be retrieved in the Information Mode by hovering over the monitor.

### Workflow Illustration

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689867730/DataImportWizard-4-Discretization-R2-GenOpt_a0up73.mp4" %}

\
