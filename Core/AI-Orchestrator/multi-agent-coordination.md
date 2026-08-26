# Multi Agent Coordination

Context: [AI-Orchestrator](README.md).

## Purpose

Coordinate justified independent contributions and reconcile conflicts.

## When to Use

Independent parallel contributions materially reduce latency or improve a high-stakes review, and delegation is available and authorized. Otherwise coordinate roles within one agent.

## Boundary

Consultants return evidence; they do not become competing owners.

## Inputs

Lead owner, separable tasks, shared constraints, available agents, task-level budget, writable resources and acceptance rules.

## Method

1. Justify each worker by an independent contribution or blind critique. Do not assign several personas the same final deliverable. Parallelize only tasks whose needed inputs are ready; sequence dependent findings.
2. Give bounded contracts and minimal raw artifacts. For an independent evaluation, withhold the expected answer and prior verdict unless regression testing needs them. Distinguish different reviewers from genuinely independent evidence sources.
3. Assign nonoverlapping write ownership or keep reviewers read-only. Coordinate changes through the lead; no worker may widen scope, launch more workers or borrow another task’s authority without an actual mandate.
4. Collect source-backed results, uncertainties, tested cases and unresolved questions. Reconcile differing scope, definitions, data versions and assumptions before treating disagreement as substantive.
5. Resolve factual conflict with a discriminating check; domain-rule conflict goes to the qualified owner; preference conflict goes to the actual decision maker. The lead synthesizes one outcome and records unresolved material dissent.

## Bounded Coordination

Maintain a task dependency graph and a task-level budget shared across workers. Refuse circular handoffs: a worker returns its unresolved question to the lead rather than delegating it back through another persona. Limit critique to findings that can change acceptance or the decision, with a named next test and stopping condition. Agreement among agents using the same source/model is not independent corroboration; voting cannot resolve missing facts or authorize an action.

## Output

Contribution map, accepted results with provenance, conflict disposition, integrated result and any cancelled/unneeded work.

## Quality Checks

- No file/resource has competing writers and no final recommendation is attributed to an unconsulted specialist.
- Every repeated review has a concrete hypothesis or regression purpose; stop when acceptance is supported or the remaining blocker is external.

## Handoffs

The lead uses [output-evaluation](output-evaluation.md). [Critical-Thinking](../Critical-Thinking/README.md) may test an inference; it does not become a second task owner.
