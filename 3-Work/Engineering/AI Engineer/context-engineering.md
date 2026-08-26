# Context Engineering

Context: [AI Engineer](README.md).

## Purpose

Assemble the minimum trustworthy information needed for a model decision.

## Activate When

Long histories, retrieved documents, memory, or tools create missing, stale, conflicting, or excessive context.

## Do Not Use When

Prompt-engineering defines task instructions; retrieval-design finds evidence. Context assembly does not grant access to data.

## Required Context

**Needed:** Task, context sources, trust/permission boundaries, model budget, and freshness requirements.

**Can be deferred or bounded:** Detailed token budgets may be tuned experimentally; identity/tenant scope and authoritative sources cannot be guessed.

## Workflow

1. Inventory instructions, user data, retrieved evidence, tool results, conversation state, and memory. Assign provenance, trust level, freshness, and allowed use.
2. Budget space for the task, relevant evidence, output, and tool interaction. Select by decision relevance; preserve source identifiers, units, dates, unresolved contradictions, and exact constraints.
3. Define truncation, summarization, and memory rules. Keep durable facts separate from temporary hypotheses; require correction and deletion propagation across summaries and stores.
4. Evaluate missing decisive evidence, conflicting versions, long histories, malicious source text, and cross-tenant retrieval. Compare shorter and larger context packs by task success.
5. Version the assembly policy and record which evidence informed each result without retaining sensitive raw text by default.

## Decision Rules

- If compaction removes a material rule or source qualification, regenerate the summary or fetch the source before deciding.
- If sources disagree, retain the contradiction and authority basis rather than averaging or silently choosing the latest text.

## Output Contract

Context assembly contract with source priority, budget, provenance, refresh/deletion rules, test results, and unavailable-context behavior.

## Quality Gates

- A traced answer can identify the actual source versions used.
- Cross-session and cross-tenant cases do not inherit unrelated private context.

## Failure Modes

- Context window size treated as useful memory capacity.
- Summary promotes tentative claims to durable facts.

## Handoffs

retrieval-design supplies selected evidence; Backend/Database enforce scope and lifecycle; Security reviews memory and tool-output trust.
