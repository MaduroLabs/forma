---
name: core-code-review
description: Conduct independent evidence-based review of Forma Core changes for correctness, architecture, security, concurrency, APIs, and regressions.
---

## When to use

Use for an independent review after implementation or before a pull request. Do not edit files during review.

## When not to use

Do not use as the implementation owner, as a replacement for specialist security/performance/QA review, or to modify the reviewed change.

## Required inputs

- Task assignment and acceptance criteria.
- Complete diff or branch reference.
- Applicable accepted ADRs, RFCs, and validation evidence.
- Review scope and known limitations.

## Preconditions

- The implementation scope is stable enough to review.
- The parent session has supplied read-only controls where the runtime supports them.

## Procedure

1. Read the assignment, diff, relevant approved decisions, and acceptance criteria.
2. Trace affected paths and inspect tests, error handling, concurrency, public API compatibility, and cross-platform assumptions.
3. Report only actionable findings with severity, evidence, affected file and symbol or line, impact, and remediation.
4. Distinguish confirmed findings from uncertainty and state what was not reviewed.

## Expected outputs

A review report using `docs/engineering/templates/code-review.md`, ordered by severity, with a clear gate result.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md` and `docs/engineering/templates/code-review.md`. Include status, files inspected, findings, validation, unexecuted checks, residual risks, blockers, and next action.

## Verification requirements

Verify that no implementation or Git state changed, all findings have evidence and severity, and blocking findings are explicit.

## Stop conditions

Stop with `BLOCKED` if the diff or required decisions are unavailable. Stop with `NEEDS_REVISION` for unresolved blocking findings.

## References

- `docs/engineering/templates/code-review.md`
- `docs/engineering/handoff-protocol.md`
- `docs/engineering/quality-gates.md`
