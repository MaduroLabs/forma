---
name: core-workflow-design
description: Design declarative workflow validation and reliable execution semantics for scheduling, state, retries, cancellation, checkpointing, and recovery.
---

## When to use

Use for workflow definitions, DAG validation, scheduling, state machines, task lifecycle, retries, side effects, checkpoints, crash recovery, or observability.

## When not to use

Do not use to design durable storage representation, database migrations, or product skill manifests. Use `core-persistence-design` or `core-skill-runtime-design` for those boundaries.

## Required inputs

- Workflow and task invariants, dependencies, legal transitions, terminal states, and side-effect requirements.
- Applicable architecture decisions and recovery expectations.

## Preconditions

- Provider and hardware assumptions are separated from workflow semantics.
- Persistence-sensitive decisions are identified for the persistence owner and Project Owner.

## Procedure

1. Define workflow and task invariants, legal transitions, dependencies, and terminal states.
2. Describe retry, cancellation, checkpoint, restart, idempotency, timeout, and external-side-effect semantics.
3. Identify what is durable, observable, and recoverable after process or machine failure.
4. Compare scheduler complexity against correctness and recovery guarantees.
5. Add contract and fault-injection acceptance criteria; request approval for persistence or public semantics.

## Expected outputs

A state and execution proposal or review with transition tables, failure matrix, recovery guarantees, risks, and tests.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include state/transition tables, recovery semantics, persistence handoff questions, files inspected or changed, validation criteria, risks, blockers, and next action.

## Verification requirements

Verify that failures are observable, side effects are explicit, legal transitions are complete, and the design does not assume a specific provider or hardware.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` for persistence, public workflow, or external-side-effect semantics. Stop with `BLOCKED` when required invariants or failure expectations are unavailable.

## References

- `docs/architecture/principles.md`
- `.agents/skills/core-persistence-design/SKILL.md`
- `.agents/skills/core-reliability-testing/SKILL.md`
- `docs/engineering/quality-gates.md`
