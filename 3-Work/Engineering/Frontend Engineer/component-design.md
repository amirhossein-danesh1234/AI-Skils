# Frontend Engineer — Component Design

Context: [Frontend Engineer](README.md).

## Purpose

Implement reusable frontend components with explicit behavior and accessible interfaces.

## Activate When

Repeated UI behavior needs a maintainable code component.

## Do Not Use When

UI Designer defines visual variants; do not turn unrelated interactions into one configurable component.

## Required Context

**Needed:** Real consumers, approved behavior/states, and framework conventions.

**Can be deferred or bounded:** An API can be proposed before implementation; do not introduce unused configuration to anticipate hypothetical consumers.

## Workflow

1. Inspect existing components and identify the smallest shared behavior.
2. Define props, events, controlled versus internal state, and semantic HTML or platform roles.
3. Implement loading, disabled, error, focus, and content extremes without hidden side effects.
4. Test public behavior and representative composition rather than private implementation details.

## Public Contract

Define controlled/uncontrolled ownership, event ordering, semantics, focus, and loading/disabled differences. Use composition when consumers share appearance but not behavior. Test invalid prop combinations and a consumer unmounting while an asynchronous action is pending.

## Decision Rules

- If two use cases share appearance but not behavior, compose primitives instead of adding many flags.
- If a component owns external effects, expose their contract and cancellation behavior.

## Output Contract

Component API and implementation with state coverage, composition rules, tests, and usage examples appropriate to the codebase.

## Quality Gates

- Can keyboard and assistive-technology users operate it?
- Are invalid prop combinations prevented or handled clearly?
- Tests assert the public interaction contract rather than private state layout.

## Failure Modes

- Overgeneralized API: require real consumers for variants.
- Tests mirror implementation: assert observable behavior.

## Handoffs

UI Designer confirms visual contract; UX Designer confirms interaction; QA validates critical compositions.
