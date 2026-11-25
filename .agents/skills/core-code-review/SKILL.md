---
name: core-code-review
description: Conduct independent evidence-based review of Forma Core changes for correctness, architecture, security, concurrency, APIs, and regressions.
---

Use for an independent review after implementation or before a pull request. Do not edit files during review.

Procedure:

1. Read the assignment, diff, relevant approved decisions, and acceptance criteria.
2. Trace affected paths and inspect tests, error handling, concurrency, public API compatibility, and cross-platform assumptions.
3. Report only actionable findings with severity, evidence, affected file and symbol or line, impact, and remediation.
4. Distinguish confirmed findings from uncertainty and state what was not reviewed.

Expected output: a review report using `docs/engineering/templates/code-review.md`, ordered by severity, with a clear gate result.

Verify that no implementation or Git state changed and that blocking findings are explicit.
