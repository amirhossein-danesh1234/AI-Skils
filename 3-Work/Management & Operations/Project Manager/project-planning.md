# Project Planning

Context: [Project Manager](README.md).

## Purpose

Turn approved scope into a feasible delivery plan with explicit uncertainty.

## Activate When

A project starts, changes materially, or needs recovery planning.

## Do Not Use When

Product Manager chooses product value and scope; Team Manager controls staffing authority.

## Required Context

**Needed:** Approved outcome/scope, acceptance, actual capacity, dependency owners, and deadline basis.

**Can be deferred or bounded:** Initial estimates may be ranges or discovery tasks; no exact date should be manufactured from a target.

## Workflow

1. Inspect approved scope and distinguish fixed commitments from preferences.
2. Break the outcome into verifiable deliverables and identify technical, approval, vendor, and operational dependencies.
3. Estimate ranges with implementers and calculate usable capacity after support, leave, coordination, and uncertainty.
4. Sequence the dependency network, identify the critical constraint, and assign milestone evidence.
5. Test downside schedules and negotiate scope, timing, or capacity rather than hiding infeasibility.

## Delivery Plan Contract

For each work package, record deliverable, accountable owner, priority, estimate range, prerequisites, earliest feasible start, completion evidence, and unresolved decisions. Use a table only when it improves comparison. Include integration, review, test data, security checks, release, support, and operational handoff when the outcome requires them.

Calculate capacity from actual calendars and commitments. Subtract support, leave, recurring obligations, and coordination; account for skill bottlenecks and onboarding. Do not assume every person is interchangeable or that parallel work has no coordination cost. Keep contingency visible rather than hiding padding in every estimate.

Trace the dependency network and identify the path or scarce resource that controls completion. Distinguish a contractual deadline from a desired target and a forecast. If the target is infeasible, present explicit options: reduce scope, sequence differently, delay, add specifically useful capacity, accept a defined risk, or stop. Do not manufacture a plan that appears to satisfy incompatible constraints.

Use milestones with demonstrable outcomes and decision gates. Establish when estimates will be refreshed and what variance triggers escalation. Record the approved baseline and later changes so the team can distinguish execution variance from scope change.

Before handoff, run a downside walkthrough: a dependency is late, a specialist is unavailable, or testing exposes rework. Explain which buffer or decision absorbs the event and what commitment changes. A plan is ready when owners understand their outcomes, capacity is confirmed or explicitly conditional, and the sponsor can see unresolved trade-offs.

## Capacity Reconciliation

Declare the denominator of capacity deductions: support as share of gross time differs from share after leave. Avoid subtracting the same obligation twice. Model scarce skills and external approvals before parallelizing work; adding a generic person cannot remove a specialist or approval bottleneck immediately.

## Decision Rules

- If required work exceeds capacity, present explicit trade-offs to the sponsor.
- If estimates are immature, schedule discovery and use forecast ranges instead of false dates.

## Output Contract

Plan with work packages, owners, priorities, dependencies, estimates, milestones, buffers, risks, and definition of done.

## Quality Gates

- Does every deliverable have an owner and acceptance condition?
- Does the plan remain coherent with buffers and dependencies rather than 100% utilization?
- A downside walkthrough exposes a feasible response or an explicit sponsor trade-off.

## Failure Modes

- Task list mistaken for plan: add sequence and capacity.
- Deadline reverse-engineered into estimates: preserve evidence.

## Handoffs

Product Manager confirms scope; engineering estimates; Team Manager confirms capacity; sponsor approves trade-offs.
