---
name: core-release-management
description: Prepare reproducible CI, packaging, versioning, and release-readiness checks without publishing or merging.
---

Use when a task concerns GitHub Actions, Cargo packaging, dependency hygiene, semantic versioning, release artifacts, or reproducible builds.

Procedure:

1. Confirm the release scope and required authorization.
2. Validate manifests, dependency locks, platform matrix, build reproducibility, package contents, version policy, and release notes.
3. Run safe local checks and record environment, commands, artifacts, and failures.
4. Prepare but do not publish a package or release without explicit Project Owner authorization.

Expected output: a release-readiness report with CI or packaging diff, validation evidence, platform gaps, and authorization status.

Verify that no production release, package publication, auto-merge, or protection-setting change occurred.
