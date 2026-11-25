---
name: core-workflow-design
description: Design declarative workflow validation and reliable execution semantics for scheduling, state, retries, cancellation, checkpointing, and recovery.
---

Use for workflow definitions, DAG validation, scheduling, state machines, task lifecycle, retries, side effects, checkpoints, crash recovery, or observability.

Procedure:

1. Define workflow and task invariants, legal transitions, dependencies, and terminal states.
2. Describe retry, cancellation, checkpoint, restart, idempotency, timeout, and external-side-effect semantics.
3. Identify what is durable, observable, and recoverable after process or machine failure.
4. Compare scheduler complexity against correctness and recovery guarantees.
5. Add contract and fault-injection acceptance criteria; request approval for persistence or public semantics.

Expected output: a state and execution proposal or review with transition tables, failure matrix, recovery guarantees, risks, and tests.

Verify that failures are observable, side effects are explicit, and the design does not assume a specific provider or hardware.
