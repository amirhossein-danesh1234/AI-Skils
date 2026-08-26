# Usability Analysis

Context: [Product Designer-UX Designer](README.md).

## Purpose

Assess whether users can complete intended tasks with acceptable effort and error.

## Activate When

A design or live flow needs evidence of comprehension and task success.

## Do Not Use When

Do not infer usability solely from aesthetic quality or a heuristic checklist.

## Required Context

**Needed:** Goal-based tasks, relevant participants or explicit heuristic scope, and success criteria.

**Can be deferred or bounded:** A small sample can reveal mechanisms but cannot establish population rates; telemetry may be triangulated later.

## Workflow

1. Define realistic tasks without telling participants which controls to use.
2. Observe completion, hesitation, errors, assistance, and recovery using consented methods.
3. Distinguish design defects from unfamiliarity, technical failure, and task wording bias.
4. Relate findings to task impact and propose a targeted retest.

## Observation Record

Record task outcome, unaided/assisted status, critical error, recovery, and observation timestamp. Separate user preference from demonstrated inability. Rank severity by consequence and recoverability; recurring minor hesitation is not automatically more urgent than one reproducible data-loss path.

## Decision Rules

- If users need moderator hints, do not count unaided success.
- If a small sample reveals a severe repeatable block, fix or test it without claiming population prevalence.

## Output Contract

Task-level findings, observed failures, effort indicators, severity, and prioritized changes.

## Quality Gates

- Are success criteria and assistance rules explicit?
- Are conclusions grounded in observations rather than participant approval?
- A moderator intervention is recorded and cannot be counted as unaided completion.

## Failure Modes

- Leading tasks produce false success: use goal-based prompts.
- Averages hide critical failures: report task and segment detail.

## Handoffs

Product Analyst triangulates telemetry; Frontend Engineer investigates technical failures; Product Manager decides scope.
