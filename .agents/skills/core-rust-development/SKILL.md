---
name: core-rust-development
description: Implement approved Forma Core Rust changes with explicit ownership, async, error, storage, concurrency, and cross-platform verification.
---

Use for approved Rust implementation work. Do not use this skill to invent product architecture or begin M0 during A0.

Procedure:

1. Read the assignment, applicable ADRs or RFCs, and the exact file ownership scope.
2. Inspect existing code and tests before editing. Keep the smallest change that satisfies the approved behavior.
3. Handle ownership, borrowing, async cancellation, thread safety, errors, storage boundaries, and platform differences explicitly.
4. Add focused tests for changed behavior without weakening existing tests.
5. Run applicable formatter, compiler, linter, and tests; record skipped commands and reasons.

Expected output: changed file list, implementation summary, assumptions, validation commands and results, residual risks, and handoff state.

Verify that no unrelated file changed, no secret or provider-specific coupling was introduced, and all error paths are observable.
