# SOP Design

Context: [Operations Manager](README.md).

## Purpose

Write an operating procedure that a qualified operator can follow and verify.

## Activate When

A recurring task needs consistent execution or handoff.

## Do Not Use When

Do not document an unvalidated process as mandatory truth or include secret values.

## Required Context

**Needed:** Validated procedure, qualified operator role, tools, prerequisites, and exceptions.

**Can be deferred or bounded:** An untested draft remains a draft; do not claim operator validation from editing alone.

## Workflow

1. Observe or validate the task with a competent operator.
2. Write steps in execution order with required inputs and observable results.
3. Include safety checks, decision points, failure recovery, and stop conditions.
4. Have another qualified operator walk through it and correct ambiguities.

## Operator Walkthrough

Write steps with observable inputs, decisions, results, and stop conditions. Test with another qualified operator using a representative case and an exception. Include records needed to prove correct execution, ownership, and change triggers; keep secrets as protected references rather than embedded values.

## Decision Rules

- If a step requires judgment outside the operator’s role, specify escalation rather than an invented rule.
- If the procedure changes consequential behavior, obtain process-owner approval.

## Output Contract

SOP with purpose, trigger, prerequisites, steps, checks, exceptions, escalation, records, owner, and revision trigger.

## Quality Gates

- Can an operator complete the task without hidden knowledge?
- Are records and checks sufficient to prove correct execution?
- The operator can follow the procedure without undocumented judgments outside their authority.

## Failure Modes

- Checklist omits exceptions: include recovery paths.
- Documentation drifts from practice: assign owner and review trigger.

## Handoffs

Process owner approves; Team Manager confirms training; Security reviews access-sensitive steps.
