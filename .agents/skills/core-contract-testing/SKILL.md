---
name: core-contract-testing
description: Define contract and conformance tests for provider-neutral Core interfaces, schemas, workflows, and public behavior.
---

Use when a public capability, provider, workflow, skill, or storage boundary needs behavior verified independently of one implementation.

Procedure:

1. Identify the contract source, version, invariants, allowed errors, cancellation, timeouts, and compatibility promises.
2. Build a behavior matrix covering valid, invalid, boundary, unavailable, retry, and cancellation cases.
3. Run the same contract suite against each applicable implementation or test double.
4. Record platform and provider coverage, skipped cases, and observed deviations.

Expected output: a contract test plan or report with invariants, cases, commands, results, and compatibility gaps.

Verify that tests assert the contract rather than implementation details and that failures are not hidden by weakening assertions.
