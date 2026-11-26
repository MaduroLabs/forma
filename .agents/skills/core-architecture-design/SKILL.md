---
name: core-architecture-design
description: Analyze or propose Forma Core architecture, boundaries, traits, dependencies, and compatibility without finalizing unapproved contracts.
---

## When to use

Use for architecture exploration, design review, interface boundaries, dependency decisions, or abstraction trade-offs.

## When not to use

Do not use as a substitute for provider, routing, workflow, persistence, or skill-runtime analysis when the decision is confined to one domain. Do not use to authorize implementation.

## Required inputs

- Concrete use cases and acceptance criteria.
- Project vision, scope, non-goals, and architecture principles.
- Existing accepted ADRs, relevant RFCs, and compatibility constraints.

## Preconditions

- The task has a named decision or boundary to analyze.
- The owning domain specialist is identified when the work concerns providers, routing, workflows, persistence, or product skills.

## Procedure

1. Read `docs/project/vision.md`, `scope.md`, `non-goals.md`, and `docs/architecture/principles.md`.
2. Identify the concrete use cases, invariants, ownership boundaries, and compatibility surface.
3. Compare at least two viable alternatives when the decision is material, including trade-offs, failure modes, migration cost, and premature-abstraction risk.
4. Mark every statement as an approved decision, proposal, verified fact, assumption, open question, or limitation.
5. Put proposed contracts in an RFC and approved decisions in an ADR only after the required human approval.

## Expected outputs

An architecture proposal or review with alternatives, risks, affected boundaries, explicit approval requests, and a verification plan.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include the decision status, alternatives, affected boundaries, inspected files, assumptions, approval questions, evidence, and next action.

## Verification requirements

Verify that UI, business-domain, model-family, provider, hardware, and OS concerns do not leak into generic Core abstractions; domain boundaries are explicit; and no implementation is presented as approved design.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` before finalizing a public API, persistence guarantee, provider interface, security policy, compatibility rule, or breaking change.

## References

- `docs/project/vision.md`
- `docs/project/scope.md`
- `docs/project/non-goals.md`
- `docs/architecture/principles.md`
- `docs/rfc/README.md`
- `docs/adr/README.md`
