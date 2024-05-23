# Normalize Equal Distance

### Context

* Normalized Equal Distance is one of the [Automatic Discretization](./) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](../../) of the [Data Import Wizard](../../../).

### Algorithm Details & Recommendations

* The Normalized Equal Distance algorithm pre-processes the data with a smoothing algorithm to remove outliers before computing equal partitions.
* As a result, the algorithm is less sensitive to outliers than the Equal Distance algorithm.&#x20;
* The algorithm also takes into account the Minimum Interval Weight that defines the minimum prior probability of a bin.
* You can adjust the default Minimum Interval Weight under `Main > Menu > Window > Preferences > Discretization`.
