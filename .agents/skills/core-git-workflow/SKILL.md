---
name: core-git-workflow
description: Apply Forma Core trunk-based branch, commit, pull-request, scope, and human-approval rules safely.
---

Use for branch setup, status checks, commit preparation, pull request preparation, or Git handoffs.

Procedure:

1. Inspect branch, remote, working tree, and latest `main` before changing Git state.
2. Preserve unrelated user changes and create one dedicated branch per milestone or task.
3. Keep commits scoped and reviewable; inspect the complete diff and run `git diff --check`.
4. Push only the dedicated branch and prepare a pull request targeting `main`.
5. Stop after opening the pull request. Do not merge, enable auto-merge, force-push, bypass rules, or modify protection settings.

Expected output: branch and commit summary, diff scope, validation evidence, and pull request URL or an explicit blocker.

Verify that no unrelated changes or secrets entered the commit and that human merge authority remains intact.
