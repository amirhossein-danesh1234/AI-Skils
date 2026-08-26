# AI Use Case Analysis

Context: [AI Engineer](README.md).

## Purpose

Decide whether probabilistic AI behavior is suitable for a bounded product task.

## Activate When

An AI feature is proposed or an existing manual/rule-based task appears costly.

## Do Not Use When

Product Manager decides user value; Founder Advisor decides company investment. AI is not the default implementation.

## Required Context

**Needed:** User task, current baseline, representative inputs, desired outputs, error consequences, and permitted data/actions.

**Can be deferred or bounded:** Exact model and budget may be deferred for feasibility; production acceptance requires owner-approved quality, cost, latency, and risk limits.

## Workflow

1. Define the task unit and measurable success, including how a user recognizes failure. Separate drafting, recommending, deciding, and acting because their consequences differ.
2. Compare deterministic rules, search, improved UX, human service, single model call, retrieval, and agentic execution. Identify why the simplest adequate baseline fails.
3. Map common, ambiguous, unsupported, adversarial, and high-consequence cases. Check whether correct outcomes can be judged and whether lawful usable evidence exists.
4. Estimate full task cost including review, retries, integration, exceptions, and failure. Identify an abstention or non-AI path before a pilot.
5. Recommend reject, non-AI solution, assistive pilot, or constrained automation. Specify the evaluation dataset, decision gates, exposure cap, and owner before model experimentation.

## Decision Rules

- If errors cannot be detected or safely contained at acceptable cost, reduce autonomy or reject the use case.
- If a deterministic solution meets the task, do not add an LLM solely for novelty.

## Output Contract

Feasibility brief: task contract, baseline comparison, harm model, data feasibility, economics, autonomy level, pilot/evaluation gates.

## Quality Gates

- A representative case has a judgeable outcome and a safe failure path.
- Pilot success cannot be declared solely from selected demonstrations.

## Failure Modes

- Fluent output mistaken for completed task.
- Human review assumed unlimited or infallible.

## Handoffs

Product Manager validates value and policies; Founder Advisor weighs resources; Security reviews data exposure; evaluation-design defines evidence.
