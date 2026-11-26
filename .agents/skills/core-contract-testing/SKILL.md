---
name: core-contract-testing
description: Define contract and conformance tests for provider-neutral Core interfaces, schemas, workflows, and public behavior.
---

## When to use

Use when a public capability, provider, workflow, skill, or storage boundary needs behavior verified independently of one implementation.

## When not to use

Do not use for implementation-detail unit tests, isolated fault-recovery testing, or architecture decisions that have no testable contract yet.

## Required inputs

- Contract source and version.
- Invariants, allowed errors, cancellation, timeouts, and compatibility promises.
- Applicable implementations or test doubles.
- Platform/provider coverage expectations.

## Preconditions

- The contract is approved or explicitly assigned as a proposal under test design.
- The behavior under test can be observed without relying on implementation internals.

## Procedure

1. Identify the contract source, version, invariants, allowed errors, cancellation, timeouts, and compatibility promises.
2. Build a behavior matrix covering valid, invalid, boundary, unavailable, retry, and cancellation cases.
3. Run the same contract suite against each applicable implementation or test double.
4. Record platform and provider coverage, skipped cases, and observed deviations.

## Expected outputs

A contract test plan or report with invariants, cases, commands, results, and compatibility gaps.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md` and, where applicable, `docs/engineering/templates/qa-report.md`. Include the contract version, matrix, files inspected or changed, commands, results, skipped cases, deviations, risks, and next action.

## Verification requirements

Verify that tests assert the contract rather than implementation details, failures are not hidden by weakened assertions, and environment failures are distinguished from contract failures.

## Stop conditions

Stop with `BLOCKED` if the contract version or implementation under test is unavailable. Stop with `NEEDS_HUMAN_APPROVAL` if the test would establish an unapproved public contract.

## References

- `docs/engineering/testing-strategy.md`
- `docs/engineering/templates/qa-report.md`
- `docs/engineering/quality-gates.md`
