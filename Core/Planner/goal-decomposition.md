# Goal Decomposition

Context: [Planner](README.md).

## Purpose

Map outcomes to necessary sub-outcomes and acceptance evidence.

## When to Use

An accepted goal is too broad to assign or verify directly.

## Boundary

Orchestrator decomposition defines agent contributions, not outcome scope.

## Inputs

Goal, beneficiary, success measures, scope exclusions, constraints and accountable owner.

## Method

1. Express the goal as a change or accepted result, not an activity label. Separate what the task can control from outcomes it can only influence.
2. Identify necessary sub-outcomes and their dependency relations. Ask whether achieving the proposed children is sufficient for the parent or merely produces inputs.
3. For each leaf, define a deliverable, acceptance evidence and owner. Stop splitting when it can be estimated and verified without unnecessary microtasks.
4. Trace every leaf upward to the goal and every goal condition downward to evidence. Remove unrelated work and expose missing integration or adoption conditions.
5. Distinguish outcome milestones from learning gates: a test may complete a learning goal even when it rejects the hoped-for solution.

## Necessary Is Not Sufficient

A list of completed tasks may fail to produce the desired outcome. Identify the bridge from output to use and from use to benefit, including external dependencies beyond the team’s control. Do not make an uncontrollable result a falsely guaranteed deliverable; state the contribution and evidence that can actually be accepted.

## Output

A compact outcome tree or ordered map with leaf acceptance, dependencies, owners and explicit scope exclusions.

## Quality Checks

- No parent is marked complete solely because its activity checklist is complete.
- Negative evidence can satisfy a valid learning milestone without being relabeled failure.

## Handoffs

[Task-decomposition](../AI-Orchestrator/task-decomposition.md) turns selected work into agent contribution contracts; [timeline-design](timeline-design.md) handles scheduling.
