---
name: core-git-workflow
description: Apply Forma Core trunk-based branch, commit, pull-request, scope, and human-approval rules safely.
---

## When to use

Use for branch setup, status checks, commit preparation, pull request preparation, or Git handoffs.

## When not to use

Do not use to merge pull requests, enable auto-merge, change branch protection, publish releases, or discard unrelated user changes.

## Required inputs

- Authorized task or milestone.
- Current branch, remote, working-tree, and base-branch state.
- Intended file scope and validation evidence.
- Existing PR identity, when resuming delivery.

## Preconditions

- The working tree has been inspected and unrelated changes are preserved.
- The target branch is `main` and the dedicated feature branch is authorized.

## Procedure

1. Inspect branch, remote, working tree, and latest `main` before changing Git state.
2. Preserve unrelated user changes and create one dedicated branch per milestone or task.
3. Keep commits scoped and reviewable; inspect the complete diff and run `git diff --check`.
4. Push only the dedicated branch and prepare a pull request targeting `main`.
5. Stop after opening the pull request. Do not merge, enable auto-merge, force-push, bypass rules, or modify protection settings.

## Expected outputs

Branch and commit summary, diff scope, validation evidence, and pull request URL or an explicit blocker.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include branch, base SHA, commit SHA, changed paths, diff validation, push result, PR identity/target, CI state, blockers, and next action.

## Verification requirements

Verify that no unrelated changes or secrets entered the commit, `git diff --check` passes, the branch is not `main`, PR target is `main`, and human merge authority remains intact.

## Stop conditions

Stop with `BLOCKED` when remote or GitHub authorization is unavailable. Provide the verified branch, commit, comparison URL, PR title/body, and manual next action. Do not claim a PR exists without verification.

## References

- `docs/engineering/git-workflow.md`
- `docs/engineering/handoff-protocol.md`
- `docs/engineering/quality-gates.md`
