# Equal Frequency

### Context

* Equal Frequency is one of the [Automatic Discretization](./) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](../../) of the [Data Import Wizard](../../../).

### Algorithm Details & Recommendations

* This Equal Frequency algorithm defines thresholds so that each interval contains the same number of observations.
* This approach typically produces a uniform distribution.
* As a result, the shape of the original density function is no longer apparent upon discretization.
* This also leads to an artificial increase in the entropy of the system, directly affecting the complexity of machine-learned models.
* However, this type of discretization can be useful — once a structure is learned — for further increasing the precision of the representation of continuous values.
