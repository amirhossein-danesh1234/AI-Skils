# Task Breakdown

Context: [Project Manager](README.md).

## Purpose

Decompose a deliverable into executable work without losing the outcome.

## Activate When

A plan is too coarse to estimate, assign, or track.

## Do Not Use When

Do not split work into arbitrary tiny tasks or dictate implementation detail beyond evidence.

## Required Context

**Needed:** Deliverable, acceptance, likely approach, and dependencies.

**Can be deferred or bounded:** Fine implementation detail belongs to implementers; uncertain work can be a bounded discovery package.

## Workflow

1. Start from the accepted deliverable and identify necessary artifacts or behavior.
2. Split by verifiable outputs and meaningful risk boundaries.
3. Include integration, review, test data, deployment, documentation, and operational handoff where needed.
4. Check coverage and remove duplicate or unnecessary tasks.

## Coverage Walk

Walk the deliverable from setup through integration, review, test, release, support, and handoff, selecting only relevant work. Each package needs an output, owner, dependencies, and completion evidence. Combine fragments whose separation adds coordination without a verifiable intermediate outcome.

## Decision Rules

- If a task has no observable completion condition, refine it.
- If decomposition creates excessive coordination, combine work around a coherent owner.

## Output Contract

Work packages with outputs, owners, estimates, dependencies, and completion checks.

## Quality Gates

- Do tasks collectively produce the deliverable and nothing unrelated?
- Are hidden integration and validation work represented?
- The packages collectively produce the accepted outcome without omitted integration or validation effort.

## Failure Modes

- Only coding tasks counted: include readiness work.
- Task count mistaken for progress: track accepted outputs.

## Handoffs

Implementers validate decomposition; QA supplies verification work; Team Manager confirms ownership.
