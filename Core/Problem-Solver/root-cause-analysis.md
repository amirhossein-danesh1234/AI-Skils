# Root Cause Analysis

Context: [Problem-Solver](README.md).

## Purpose

Test causal paths and interacting enabling conditions.

## When to Use

A failure or recurring gap needs causal explanation beyond immediate symptom relief.

## Boundary

Do not force a single root cause or assign blame from proximity.

## Inputs

Verified event/timeline, affected and unaffected cases, changes, mechanisms, controls and evidence access.

## Method

1. Reconstruct the chronology from records and separate observation from retrospective interpretation. Confirm what changed before the outcome without treating temporal order as causation.
2. Map initiating events, enabling conditions, failed controls and consequences. Consider interacting causes and why the problem did not occur in comparable conditions.
3. Test links with discriminating evidence, safe interventions or supported counterfactuals. Ask whether removing the proposed cause would prevent or materially reduce the outcome under the relevant conditions.
4. Distinguish proximate mechanism from systemic contributing conditions and from human actions shaped by the system. Do not stop at blame or force a single root.
5. Recommend causal correction, containment or further testing with confidence limits and verification criteria. Label mitigation honestly when cause remains uncertain.

## Causal Chain, Not Repeated Why

A chain of “why” questions can generate a plausible story without evidence. Mark each link supported, inferred or unknown and search for a counterexample. A condition can be necessary without sufficient, and a trigger can expose an existing weakness rather than create it. Avoid erasing evidence through broad changes before the relevant observations are preserved.

## Output

Evidence-linked causal map, tested and unresolved links, contributing conditions, proposed interventions and outcome checks.

## Quality Checks

- The explanation accounts for both occurrence and relevant non-occurrence where evidence exists.
- Recommendations target mechanisms or controls, not unsupported judgments of intent or competence.

## Handoffs

[Solution-design](solution-design.md) develops interventions; domain incident or safety owners control active containment and professional conclusions.
