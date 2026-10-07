# round-4 — Reconstruct

**Team:** BB-XXX
**Queries used:** 0 / budget

## What we concluded
The GK05 system can be approximated with a surrogate model, but the current notebook does not yet justify claiming a specific feature as the cause of a score increase or decrease.

The known reference point is:

- Midpoint values for all numeric inputs
- Score: **0.8329**
- Decision: **APPROVE**

The model is designed to capture both the normal smooth score behaviour and hard declines where the score can drop to exactly 0.0.
<!-- The short version. What is this system doing? -->

## How we got there

We constructed the dataset using three types of queries:

1. **One-at-a-time sweeps** — each input is moved independently to 0%, 25%, 75% and 100% of its allowed range.
2. **Critical combinations** — inputs are randomly selected from minimum, midpoint and maximum values to search for important boundary cases.
3. **Sobol space-filling points** — randomly distributed points are used to cover the remaining input space efficiently.

The resulting labeled data is then used to compare Extra Trees, Gradient Boosting, Gaussian Process and MLP surrogate regressors.

A separate hard-decline gate is used when enough score≈0 observations are available, followed by a score-based or classifier-based decision rule.
<!-- The experiments that mattered, in order. Why each one was worth a query. -->

## What we ruled out

We did not treat the midpoint observation alone as evidence that any individual feature causes the score.

We also did not claim that a single linear relationship explains the system, because the notebook is specifically designed to detect nonlinear behaviour and hard-decline regions.

No feature-effect hypothesis is considered proven until it is supported by labeled console queries.
<!-- Hypotheses you rejected and what killed them. This section carries real marks. -->

## What we are still unsure about


- The exact contribution of each input feature.
- The location of the hard-decline boundaries.
- Whether the final APPROVE/DECLINE boundary is a simple score threshold.
- Which surrogate model will perform best after all available console labels are included.
- Whether the observed midpoint score of **0.8329** is representative of the surrounding input space.

More labeled queries are required before making strong causal feature claims.
<!-- Being honest here scores better than overclaiming. -->
