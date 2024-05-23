# Equal Distance

### Context

* Equal Distance is one of the [Automatic Discretization](./) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](../../) of the [Data Import Wizard](../../../).

### Algorithm Details & Recommendations

* The Equal Distance algorithm computes the equal distances based on the range of the variable.
* This method is particularly useful for discretizing variables that share the same variation domain (e.g. satisfaction measures in surveys).
* Additionally, this method is suitable for obtaining a discrete representation of the density function.
* However, the Equal Distance algorithm is extremely sensitive to outliers and can generate intervals that do not contain any data points. Please see the [Normalized Equal Distance](normalize-equal-distance.md) algorithm, which addresses this particular issue.
