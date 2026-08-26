# Agent Design

Context: [AI Engineer](README.md).

## Purpose

Choose and constrain a model-directed loop that can complete a task and stop safely.

## Activate When

The next step genuinely depends on observations and fixed workflows are insufficient.

## Do Not Use When

Use deterministic orchestration for known sequences; multi-agent-design requires a separate benefit case.

## Required Context

**Needed:** Task outcome, available tools, environment observations, authority, success oracle, and time/cost/action limits.

**Can be deferred or bounded:** A prototype can use simulated tools; production needs measured failure behavior and an available fallback owner.

## Workflow

1. Compare a fixed workflow or single call with model-directed iteration on the same tasks. Identify what uncertainty requires dynamic action selection.
2. Define explicit run states: plan, act, observe, verify, complete, abstain, failed, or awaiting approval. Persist necessary state and distinguish an intention from an observed effect.
3. Set budgets for elapsed time, cost, tool calls, retries, and repeated non-progress. Route irreversible actions through trusted approval and authorization gates.
4. Specify checkpoint/resume behavior, cancellation, stale state, ambiguous writes, and recovery. Resume from authoritative effects rather than trusting a narrative summary.
5. Evaluate full trajectories, not just final prose: task success, unnecessary actions, boundary violations, loops, and recovery after injected failures. Release in bounded exposure.

## Decision Rules

- If repeated actions produce no new evidence, stop, change strategy within scope, or hand off; do not loop until budget exhaustion.
- If the final answer claims an action, require authoritative tool evidence for the effect.

## Output Contract

Agent state/authority model, stop conditions, tool budget, recovery protocol, trajectory evaluation, and rollout/fallback gate.

## Quality Gates

- Cancellation and exhausted-budget tests leave a known safe state.
- Success depends on the task oracle, not the agent declaring itself finished.

## Failure Modes

- Autonomy expands until it finds a solution outside the mandate.
- Checkpoint replay duplicates external effects.

## Handoffs

Architect reviews system boundaries; tool-use-design controls actions; evaluation-design scores trajectories; DevOps operates the runtime.

## References

[Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) supports the workflow-versus-agent distinction and simple-baseline approach. Verify current provider interfaces separately; this is not a runtime dependency.
