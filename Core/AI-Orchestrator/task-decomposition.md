# Task Decomposition

Context: [AI-Orchestrator](README.md).

## Purpose

Split a task into dependency-aware, verifiable contribution contracts.

## When to Use

A task cannot be completed reliably as one unit because of independent evidence, effects or dependencies.

## Boundary

Not a new business goal or a staffing/scheduling plan.

## Inputs

User outcome, acceptance conditions, known artifacts, constraints, ownership and available capabilities.

## Method

1. Start from what the user must receive, not from a list of personas. Separate evidence gathering, interpretation, decision and authorized action only where their inputs or gates differ.
2. Create the smallest useful subproblems with testable return artifacts. For each, name prerequisites, permitted effects, consumer and definition of usable completion.
3. Draw dependency edges. Identify a path that can produce early decision-changing evidence; avoid parallel work likely to be invalidated by an unresolved policy or feasibility gate.
4. Check coverage in both directions: each requirement has an output, and each subtask serves a requirement. Remove duplicate research, duplicate synthesis and tasks included only to keep a persona busy.
5. Choose direct execution, sequential consultation or independent delegation according to dependency and actual tooling. Keep a single integrating lead and consolidate overlapping questions before dispatch.

## Cut at Evidence Interfaces

A good split allows a worker to finish from the packet without inventing another worker’s result. If two tasks repeatedly exchange partial conclusions, combine them or define a stable intermediate contract. A dependency cycle is usually a missing decision, a poorly chosen boundary or an explicit bounded iteration—not permission for circular delegation. Keep scope decomposition separate from calendars, staffing and business priorities.

## Output

A compact dependency graph or ordered work list containing outputs, prerequisites, owners, acceptance checks and justified parallelism.

## Quality Checks

- Every subtask can be accepted independently enough for its consumer to progress.
- The integration work and final verification are explicit; subtask completion alone is not task completion.

## Handoffs

[Planner goal-decomposition](../Planner/goal-decomposition.md) defines outcome scope and [timeline-design](../Planner/timeline-design.md) handles feasible timing when needed.
