# Scenario Analysis

Context: [Financial Analyst](README.md).

## Purpose

Quantify financial outcomes under coherent alternative assumptions.

## Activate When

A decision depends on uncertain drivers or downside exposure.

## Do Not Use When

Scenario analysis changes several related drivers; sensitivity changes one driver at a time.

## Required Context

**Needed:** Validated model or explicit equations, uncertain drivers, causal relationships, and decision limits.

**Can be deferred or bounded:** Probabilities are optional; scenarios can show conditional outcomes without expected-value claims.

## Workflow

1. Validate the base model before changing assumptions.
2. Define plausible combinations of demand, price, cost, timing, and funding drivers.
3. Respect causal relationships and avoid incompatible optimistic or pessimistic combinations.
4. Compare outcomes and identify thresholds where the decision changes or liquidity fails.

## Coherent Shock

Tie assumptions together through mechanisms, such as lower demand causing discounting while fixed cost remains. Keep formulas constant across scenarios and vary driver inputs. Report cash timing and constraint breaches as well as profit; show a one-way sensitivity separately when isolating a driver.

## Decision Rules

- If the downside breaches a hard constraint, identify mitigation or a smaller commitment.
- If probabilities lack evidence, do not present expected value as precise.

## Output Contract

Scenario results with assumptions, mechanisms, cash/margin effects, thresholds, and contingent actions.

## Quality Gates

- Are scenario inputs internally coherent and formulas unchanged?
- Are one-way sensitivities distinguished from multi-driver scenarios?
- A scenario is internally plausible and its action trigger is explicit.

## Failure Modes

- Arbitrary percentage shocks: tie changes to mechanisms.
- Only profit shown: inspect cash and timing.

## Handoffs

Business Strategist defines strategic futures; Commercial specialist supplies term/FX exposure; decision owner chooses response.
