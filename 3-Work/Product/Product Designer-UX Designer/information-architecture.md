# Information Architecture

Context: [Product Designer-UX Designer](README.md).

## Purpose

Organize content and actions so users can find and understand them.

## Activate When

Navigation, categories, or labels obscure tasks and content relationships.

## Do Not Use When

Do not use taxonomy work to redesign product strategy or visual styling.

## Required Context

**Needed:** Content/destination inventory, priority find tasks, and audience terminology.

**Can be deferred or bounded:** User testing can follow a provisional hierarchy; label heuristic grouping as unvalidated.

## Workflow

1. Inventory actual content and identify duplicate or missing destinations.
2. Group by user intent and mental model, not internal departments by default.
3. Define labels and hierarchy with shallow paths to frequent tasks.
4. Test representative find tasks and permission-dependent visibility; record ambiguous labels.

## Findability Probe

Give a representative user a goal without menu labels and record first choice, backtracking, and completion. Check empty and permission-reduced navigation separately. Use one canonical content destination with contextual entry links rather than duplicated pages that can disagree.

## Decision Rules

- If a category mixes incompatible user meanings, split or relabel it.
- If the same content appears in several paths, define one source and multiple entry links.

## Output Contract

Proposed hierarchy, labels, navigation rules, content ownership, and findability checks.

## Quality Gates

- Can representative users predict where a task belongs?
- Are labels consistent and inaccessible destinations handled clearly?
- A frequent task has a discoverable route even when optional sections are absent.

## Failure Modes

- Org chart copied into navigation: use task evidence.
- Deep hierarchy hides important content: test path cost.

## Handoffs

Product Manager owns content scope; UI Designer expresses hierarchy; Frontend Engineer checks routing and access states.
