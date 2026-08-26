# Agent Workflow Design

Context: [AI-Orchestrator](README.md).

## Purpose

Design context packets, execution states, interfaces and approval gates.

## When to Use

A repeatable task needs explicit states, context exchange or human gates before implementation.

## Boundary

A workflow design is not permission to launch agents or tools.

## Inputs

Task contract, input/output types, state-changing boundaries, participants, evidence locations, failure consequences and actual runtime capabilities.

## Method

1. Compare a direct response or deterministic sequence with a dynamic agent loop. Choose the least complex design that handles observed branching; hypothetical future flexibility is insufficient.
2. Define states such as ready, running, awaiting evidence/approval, verifying and terminal. Give each transition an observable condition, responsible actor and allowed effect. A generated plan is not an executed state transition.
3. Design a handoff packet: objective, question, scope exclusions, required output, approved actions, relevant source excerpts with locators/version, assumptions, completed work and remaining budget. Include only data the recipient is permitted to receive.
4. Specify context assembly: retrieve by current question, prefer authoritative artifacts over conversational recollection, retain contrary evidence, and replace stale versions explicitly. Summaries point to source evidence; they do not silently upgrade an inference to fact.
5. Walk the design through missing input, conflicting findings, unavailable tool, stale context, cancellation and approval denial. Identify who resumes, who can terminate and how terminal status reaches the user.

## Interface and State Contract

For each dependency specify producer, consumer, artifact identity, acceptance condition and failure route. A consumer acknowledges usable acceptance rather than treating a producer’s “done” as proof. Separate durable task/effect state from narrative memory; resumption must reconcile observed effects before repeating an action. Context trim must retain scope, permissions, critical counterevidence and unresolved gates. Keep implementation choices with the relevant engineering/domain owner.

## Output

A minimal state/transition map, context packet shape, dependency contracts, human gates, terminal outcomes and a few concrete failure walkthroughs.

## Quality Checks

- Every reachable nonterminal state has an owned next event or bounded timeout; no wait depends on a participant already waiting on it.
- Removing unnecessary participants or context does not change required correctness; sensitive data is not copied merely for convenience.

## Handoffs

Use [workflow-reliability](workflow-reliability.md) for retries and unknown effects. Domain engineers implement runtime mechanisms; this design does not launch them.
