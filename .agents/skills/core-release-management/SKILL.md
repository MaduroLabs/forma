---
name: core-release-management
description: Prepare reproducible CI, packaging, versioning, and release-readiness checks without publishing or merging.
---

## When to use

Use when a task concerns GitHub Actions, Cargo packaging, dependency hygiene, semantic versioning, release artifacts, or reproducible builds.

## When not to use

Do not use to publish packages, create production releases, merge pull requests, or add product CI for code that does not exist.

## Required inputs

- Release or infrastructure scope and authorization.
- Manifests, dependency locks, platform matrix, package contents, version policy, and reproducibility requirements.

## Preconditions

- Release scope and authorization are explicit.
- The repository contains the artifacts or configuration being validated, or their absence is recorded as not applicable.

## Procedure

1. Confirm the release scope and required authorization.
2. Validate manifests, dependency locks, platform matrix, build reproducibility, package contents, version policy, and release notes.
3. Run safe local checks and record environment, commands, artifacts, and failures.
4. Prepare but do not publish a package or release without explicit Project Owner authorization.

## Expected outputs

A release-readiness report with CI or packaging diff, validation evidence, platform gaps, and authorization status.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include scope, changed files, commands/results, platform coverage, dependency or supply-chain risks, unexecuted checks, authorization status, and next action.

## Verification requirements

Verify that no production release, package publication, auto-merge, or protection-setting change occurred and that dependency/CI/artifact evidence is reproducible.

## Stop conditions

Stop with `BLOCKED` when authorization or required platform/tooling is unavailable. Do not retry known authorization failures without changed conditions.

## References

- `docs/engineering/git-workflow.md`
- `docs/engineering/quality-gates.md`
- `docs/engineering/security-policy.md`
