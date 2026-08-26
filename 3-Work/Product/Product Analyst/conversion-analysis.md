# Conversion Analysis

Context: [Product Analyst](README.md).

## Purpose

Explain a change in a defined conversion rate and identify useful tests.

## Activate When

A rate differs across segments, periods, or variants.

## Do Not Use When

Funnel analysis locates steps; [experiment-analysis.md](experiment-analysis.md) evaluates randomized treatment effects.

## Required Context

**Needed:** Numerator, eligible denominator, comparison windows, and segmentation variables.

**Can be deferred or bounded:** If identity or instrumentation is unknown, deliver a data-validity diagnosis before a conversion explanation.

## Workflow

1. Validate the metric definition, tracking, and population before comparing rates.
2. Separate changes within segments from changes in traffic or customer mix.
3. Inspect seasonality, acquisition quality, eligibility, and downstream value.
4. Quantify uncertainty and test plausible mechanisms without claiming causal attribution from association.

## Rate Decomposition

Report absolute counts and percentage-point change before relative change. Reweight segment rates to a common population mix to separate composition from within-segment movement; preserve a residual when data is incomplete. Rank competing explanations by the next observation that would discriminate them, not by narrative appeal.

## Decision Rules

- If aggregate improvement reverses within segments, report the composition effect.
- If conversion rises while quality or retention falls, assess the net outcome before recommending scale.

## Output Contract

Decomposition of rate change, uncertainty, competing explanations, and recommended next test.

## Quality Gates

- Are comparable windows and populations used?
- Do uncertainty and guardrails support the recommendation?
- The same eligible population and conversion window underpin every reported rate.

## Failure Modes

- Percentage points confused with percent change: report units clearly.
- Correlation presented as cause: propose a discriminating test.

## Handoffs

Product Analyst [experiment-analysis.md](experiment-analysis.md) handles experiments; Marketing explains acquisition mix; UX examines behavior.
