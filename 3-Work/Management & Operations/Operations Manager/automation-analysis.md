# Automation Analysis

Context: [Operations Manager](README.md).

## Purpose

Decide whether a recurring task should be automated and under what controls.

## Activate When

Manual effort or errors suggest automation.

## Do Not Use When

Do not automate unstable policy, unclear ownership, or rare work without a cost case.

## Required Context

**Needed:** Observed recurring task, volume/variation, rules, failure costs, and maintenance owner.

**Can be deferred or bounded:** Early economics can use sampled times; AI suitability needs AI Engineer evidence, not an assumption that every task can be delegated to a model.

## Workflow

1. Observe the manual workflow and identify stable rules and variable judgment.
2. Compare elimination or simplification with automation.
3. Estimate build, integration, monitoring, exception, and maintenance cost against actual benefit.
4. Define human review, failure recovery, permissions, and a bounded pilot.

## Eliminate Before Automate

Compare removing the task, simplifying the process, deterministic automation, assisted judgment, and full automation. Include exception handling, monitoring, review, and recovery cost. For AI, define task-quality gates and safe fallback with AI Engineer before claiming savings.

## Decision Rules

- If inputs or policy are unstable, stabilize them before automating.
- If automation can create irreversible harm, require appropriate approval and verification controls.

## Output Contract

Automation assessment with suitability, alternatives, economics, exceptions, oversight, pilot, and stop conditions.

## Quality Gates

- Are exceptions and maintenance ownership explicit?
- Does the business case include failure and oversight cost?
- The business case measures end-to-end effort and leaves accountability with an actual owner.

## Failure Modes

- Time-saving claim ignores exceptions: model total effort.
- Automation removes accountability: retain an owner.

## Handoffs

Engineers assess deterministic implementation; AI Engineer evaluates probabilistic behavior and fallback; Security reviews permissions; Financial Analyst checks total economics.
