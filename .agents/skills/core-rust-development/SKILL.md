---
name: core-rust-development
description: Implement approved Forma Core Rust changes with explicit ownership, async, error, storage, concurrency, and cross-platform verification.
---

## When to use

Use for approved Rust implementation work. Do not use this skill to invent product architecture or implement work outside the active milestone scope.

## When not to use

Do not use for unapproved architecture, public contract design, independent review, or product implementation excluded by the active milestone.

## Required inputs

- Approved assignment, RFC/ADR, acceptance criteria, and exact file ownership.
- Existing code/tests and applicable platform constraints.

## Preconditions

- The behavior is approved for implementation.
- Ownership and validation requirements are explicit.

## Procedure

1. Read the assignment, applicable ADRs or RFCs, and the exact file ownership scope.
2. Inspect existing code and tests before editing. Keep the smallest change that satisfies the approved behavior.
3. Handle ownership, borrowing, async cancellation, thread safety, errors, storage boundaries, and platform differences explicitly.
4. Add focused tests for changed behavior without weakening existing tests.
5. Run applicable formatter, compiler, linter, and tests; record skipped commands and reasons.

## Expected outputs

Changed file list, implementation summary, assumptions, validation commands and results, residual risks, and handoff state.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include status, changed files, decisions/assumptions, validation results, unexecuted checks, residual risks, blockers, and next action.

## Verification requirements

Verify that no unrelated file changed, no secret or provider-specific coupling was introduced, all error paths are observable, and the async runtime/storage engine remains the approved choice rather than an assumption.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` if the implementation exposes an unapproved public, provider, persistence, or compatibility decision. Stop with `BLOCKED` if the approved specification or ownership scope is missing.

## References

- `docs/engineering/skill-registry.md`
- `docs/engineering/handoff-protocol.md`
- `docs/engineering/quality-gates.md`
