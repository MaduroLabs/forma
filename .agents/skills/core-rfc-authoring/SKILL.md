---
name: core-rfc-authoring
description: Draft and revise Forma Core architecture RFCs for proposed material decisions and human review.
---

## When to use

Use when a proposed change affects public APIs, persistence, provider interfaces, security policy, compatibility, or another material architectural concern.

## When not to use

Do not use for a non-material implementation detail, an accepted decision record, or a request to implement an unapproved proposal.

## Required inputs

- Decision question and affected scope.
- Project policies, existing decisions, evidence, alternatives, and acceptance criteria.

## Preconditions

- The decision is material enough to require an RFC.
- The RFC owner can identify the Project Owner approval request and relevant reviewers.

## Procedure

1. Read `docs/rfc/README.md`, relevant project policies, and existing decisions.
2. Use the template in `docs/engineering/templates/architecture-rfc.md`.
3. Use `PROPOSED` while drafting and `UNDER_REVIEW` when submitted for review. Only the Project Owner may move it to `APPROVED`, `REJECTED`, `WITHDRAWN`, or `SUPERSEDED`. Include context, decision required, goals, non-goals, alternatives, trade-offs, design, failure semantics, compatibility, security, performance, migration, acceptance criteria, and open questions.
4. Link evidence and affected files; do not state future behavior as implemented.
5. Request explicit approval and record the outcome separately from the proposal.

## Expected outputs

A reviewable RFC with a decision request and acceptance criteria.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include RFC path/status, alternatives, evidence, affected files, assumptions, approval request, open questions, and next action.

## Verification requirements

Verify that the RFC follows the lifecycle in `docs/rfc/README.md`, does not create an accepted ADR prematurely, does not include product implementation, and distinguishes facts from assumptions.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` when the RFC is ready for a material decision. Do not convert it to an accepted ADR without explicit approval evidence.

## References

- `docs/rfc/README.md`
- `docs/engineering/templates/architecture-rfc.md`
- `docs/engineering/handoff-protocol.md`
