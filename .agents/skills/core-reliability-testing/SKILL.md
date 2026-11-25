---
name: core-reliability-testing
description: Test failure recovery, cancellation, retries, idempotency, checkpoints, crash behavior, and cross-platform reliability of Core workflows.
---

Use when changes affect execution state, persistence, scheduling, external side effects, retries, recovery, or long-running operations.

Procedure:

1. List failure points and the expected durable or observable state after each failure.
2. Inject process interruption, provider failure, timeout, cancellation, partial output, duplicate delivery, and storage errors where safe.
3. Verify restart, retry, checkpoint, idempotency, and human-approval behavior.
4. Record environment, reproducibility, flakiness, and platform limits.

Expected output: a QA report with fault matrix, recovery evidence, failed or unexecuted cases, and remediation recommendations.

Verify that recovery guarantees are evidence-backed and that no test is weakened to conceal an implementation defect.
