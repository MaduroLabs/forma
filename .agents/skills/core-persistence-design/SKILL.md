---
name: core-persistence-design
description: Design Forma Core storage, durability, crash consistency, migration, checkpoint, and recovery abstractions without selecting an unapproved engine.
---

## When to use

Use for durable state, storage abstraction, transaction boundaries, crash consistency, checkpoint persistence, schema evolution, migrations, retention, artifact metadata, concurrency, corruption handling, idempotency records, or external-side-effect reconciliation.

## When not to use

Do not use for Codex session context management, workflow transition semantics, implementation, or reliability testing. Use `core-context-management`, `core-workflow-design`, `core-rust-development`, and `core-reliability-testing` for those responsibilities.

## Required inputs

- State that must survive process interruption or machine failure.
- Consistency, durability, retention, compatibility, migration, and recovery requirements.
- Workflow, side-effect, artifact, and security assumptions.

## Preconditions

- Concrete use cases justify persistence design.
- No database, filesystem, key-value store, or async runtime is treated as approved without an explicit decision.

## Procedure

1. Identify durable state and the failure boundary it must survive.
2. Define consistency, durability, transaction, recovery, and corruption-handling requirements.
3. Separate public storage contracts from implementation-specific database behavior.
4. Analyze partial writes, migrations, retention, concurrent access, version compatibility, idempotency, and external-side-effect reconciliation.
5. Compare appropriate alternatives against concrete requirements without selecting an engine by preference.
6. Define contract and fault-injection acceptance criteria.
7. Request Project Owner approval for material persistence decisions before implementation.

## Responsibility boundaries

- `core-workflow-design` owns execution semantics and legal state transitions.
- `core-persistence-design` owns durable representation, transactions, consistency, and recovery storage.
- `core-reliability-testing` verifies recovery and fault behavior.
- `core-contract-testing` verifies storage contracts independently of implementation.

## Expected outputs

A persistence proposal or review with state inventory, consistency model, transaction and recovery boundaries, alternatives, migration strategy, failure matrix, approval questions, and verification plan.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include durable-state scope, storage assumptions, alternatives, compatibility, failure modes, inspected or changed files, validation, risks, and next action.

## Verification requirements

Verify that no engine is assumed, public storage contracts are separated from implementation details, corruption and migration behavior are addressed, and exactly-once external side effects are not promised without reconciliation guarantees.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` before finalizing public persistence semantics, durability guarantees, migrations, or side-effect reconciliation. Design work does not authorize implementation; implementation requires an approved milestone and specification.

## References

- `docs/architecture/principles.md`
- `docs/rfc/README.md`
- `docs/engineering/quality-gates.md`
- `.agents/skills/core-workflow-design/SKILL.md`
- `.agents/skills/core-reliability-testing/SKILL.md`
