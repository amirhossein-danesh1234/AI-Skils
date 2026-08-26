# Risk Analysis

Context: [Decision-Analyst](README.md).

## Purpose

Trace failure paths, correlated exposure and proportionate responses.

## When to Use

A decision or plan exposes people, resources or obligations to consequential failure.

## Boundary

Domain specialists establish hazard constraints; the actual authorized risk owner accepts residual exposure within their mandate.

## Inputs

Objective, exposure horizon, failure consequences, existing controls, specialist constraints, risk owner and feasible responses.

## Method

1. Describe cause → event → consequence for material risks. Separate uncertainty about likelihood from uncertainty about impact and identify who bears the loss.
2. Estimate exposure using supported ranges, scenarios or qualitative levels with reasons. Inspect common causes, dependencies and concentration rather than treating risks as independent.
3. Use a premortem to identify overlooked enabling conditions and second-order effects. Distinguish prevention, detection, containment and recovery; a warning is not a control unless someone can act in time.
4. Compare avoid, reduce, transfer/share, stage or accept. Include control cost, new failure modes and residual exposure. Domain owners determine mandatory safeguards and unacceptable hazards.
5. Set measurable triggers, response ownership and review timing. Escalate residual exposure that exceeds the actual mandate.

## Risk Beyond a Score

Expected loss can inform repeated, comparable exposures when probabilities are defensible, but it can conceal irreversible or intolerable tail consequences. Do not multiply invented ordinal scores into precise rankings. Stress correlated failures and the capacity to recover. A low likelihood does not erase a hard domain constraint, and a mitigation proposal is not evidence that a control exists.

## Output

Prioritized failure paths, evidence/ranges, current versus proposed controls, residual exposure, trigger/owner and acceptance request.

## Quality Checks

- The assessment includes the risk of no action and of the proposed mitigation itself.
- Severe uncertainty is explicit; no risk is marked accepted solely because a persona recommended it.

## Handoffs

Domain specialists validate hazard mechanisms; [workflow-reliability](../AI-Orchestrator/workflow-reliability.md) handles orchestration failures rather than replacing this decision assessment.
