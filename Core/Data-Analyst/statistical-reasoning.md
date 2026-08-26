# Statistical Reasoning

Context: [Data-Analyst](README.md).

## Purpose

Match inference to design, dependence and uncertainty.

## When to Use

An estimate, comparison or experiment needs uncertainty or inferential interpretation.

## Boundary

No universal passing p-value or unearned causal interpretation.

## Inputs

Target quantity, study/sampling design, assignment and analysis units, data structure, model assumptions and practical decision threshold.

## Method

1. Define descriptive, predictive or causal intent. Identify sampling/assignment units, dependence, clustering, repeated observations, censoring and selection; match the method to that structure.
2. Inspect design before the result. For experiments, check randomization unit, allocation integrity, exposure, attrition, interference and planned outcomes/stopping. Observational adjustment needs defensible assumptions; it does not automatically identify causality.
3. Estimate effect magnitude with an appropriate interval and denominator. Check model fit and sensitivity to influential cases, missingness and distributional assumptions; preserve dependence in any resampling.
4. Account for multiple comparisons, repeated peeking and hypotheses discovered from the same data. Use the planned valid procedure or label the result exploratory instead of retroactively declaring confirmation.
5. Interpret uncertainty against a meaningful effect/decision threshold. A small p-value is not effect size, a probability that the hypothesis is true or an automatic action rule. Non-significance alone does not establish equivalence.

## Uncertainty Has a Source

State what the interval captures and what it omits: sampling uncertainty does not repair biased measurement or missing population coverage. A frequentist confidence level describes the procedure’s repeated-sampling coverage, not a posterior probability for this fixed parameter. Bayesian conclusions depend on stated prior/model choices. When design or sample support is inadequate, narrow to description or seek a qualified statistical review rather than applying a familiar test by default.

## Output

Estimand/design statement, method and assumptions, effect/uncertainty, sensitivity, practical interpretation and bounded causal claim if justified.

## Quality Checks

- The unit and dependence used for uncertainty match how the data were generated.
- A null or inconclusive result can complete the analysis; no threshold is altered to obtain a preferred answer.

## Handoffs

Domain experts define practical importance and design constraints. [NIST quantitative techniques](https://www.itl.nist.gov/div898/handbook/eda/section3/eda35.htm) and the [ASA p-value statement](https://www.amstat.org/asa/files/pdfs/P-ValueStatement.pdf) provide method/interpretation references, not a substitute for checking the actual design.
