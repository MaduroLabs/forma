---
name: core-reliability-testing
description: Test failure recovery, cancellation, retries, idempotency, checkpoints, crash behavior, and cross-platform reliability of Core workflows.
---

## When to use

Use when changes affect execution state, persistence, scheduling, external side effects, retries, recovery, or long-running operations.

## When not to use

Do not use for ordinary contract assertions without failure behavior, or to redesign persistence or workflow semantics.

## Required inputs

- Failure matrix and expected durable/observable state.
- Workflow and persistence decisions, side-effect semantics, environment, and platform scope.

## Preconditions

- The failure can be injected safely or the unexecuted case is documented.
- Recovery expectations are defined by the workflow and persistence owners.

## Procedure

1. List failure points and the expected durable or observable state after each failure.
2. Inject process interruption, provider failure, timeout, cancellation, partial output, duplicate delivery, and storage errors where safe.
3. Verify restart, retry, checkpoint, idempotency, and human-approval behavior.
4. Record environment, reproducibility, flakiness, and platform limits.

## Expected outputs

A QA report with fault matrix, recovery evidence, failed or unexecuted cases, and remediation recommendations.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md` and `docs/engineering/templates/qa-report.md`. Include acceptance criteria, environment, fault matrix, commands/results, failures, unexecuted checks, risks, and next action.

## Verification requirements

Verify that recovery guarantees are evidence-backed, test strength is preserved, platform limits are reported, and implementation defects are not concealed.

## Stop conditions

Stop with `BLOCKED` if the durable-state expectation or safe fault-injection method is unavailable. Stop with `NEEDS_REVISION` for failed recovery guarantees.

## References

- `docs/engineering/testing-strategy.md`
- `docs/engineering/templates/qa-report.md`
- `.agents/skills/core-persistence-design/SKILL.md`
