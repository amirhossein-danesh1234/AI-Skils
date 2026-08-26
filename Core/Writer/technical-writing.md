# Technical Writing

Context: [Writer](README.md).

## Purpose

Explain concepts or procedures with consistent states and verifiable steps.

## When to Use

A technical concept, system or procedure must be understood or followed accurately.

## Boundary

Domain experts own technical validity; prose is not executed verification.

## Inputs

Authoritative technical facts/specification, reader task, terminology, versions, prerequisites, expected states and known failure paths.

## Method

1. Define the reader’s starting knowledge and required outcome. Build a minimal concept model before instructions when unexplained terms would cause misuse.
2. For procedures, state prerequisites, scope and permission needs, then order actions by actual dependencies. Distinguish inputs, actions, expected observations and success/failure states.
3. Use consistent names, units and versions. Examples must be valid within stated assumptions; do not invent interfaces, commands or safety guarantees to make the explanation complete.
4. Explain consequential exceptions and recovery at the point of use. Separate a diagnostic observation from a corrective action and identify when qualified help or approval is needed.
5. Walk through the instructions with a representative reader or safe test where authorized. If not executed, label the verification limit; prose review is not runtime proof.

## State-Based Instructions

A procedure should let the reader tell whether to continue, stop or recover from an observed state. “Run the tool successfully” hides the needed observation. Prefer exact supported inputs and expected outcomes without prescribing domain implementation beyond the supplied evidence. A concept explanation should distinguish model simplification from physical or technical fact.

## Output

Technical explanation or procedure with terminology, prerequisites, ordered states/actions, expected outcomes, exceptions and verification status.

## Quality Checks

- A reader can identify the intended result and a failed precondition without guessing.
- Technical claims and examples match the authoritative version and actual test evidence.

## Handoffs

Domain engineers, tutors or qualified specialists own technical validity; [result-validation](../Problem-Solver/result-validation.md) checks actual outcomes where appropriate.
