---
name: core-context-management
description: Recover and reconcile the durable Forma Core project context required to begin, resume, or close engineering work.
---

## When to use

Use when starting a session, resuming interrupted work, changing machines, recovering after context compaction, continuing a milestone, receiving a merge notification, or reconciling repository and documentation discrepancies.

## When not to use

Do not use for task planning, specialist delegation, milestone state ownership, implementation, or Git publishing. Use `core-milestone-management`, `core-orchestration`, and `core-git-workflow` for those responsibilities.

## Required inputs

- Repository status, branch, remotes, and relevant commit identities.
- `docs/project/current-state.md`, active milestone documents, handoffs, RFCs, and accepted ADRs.
- Verified GitHub state when PR or CI status matters.

## Preconditions

- The repository is accessible and the current working tree can be inspected without discarding user changes.
- External state is either queryable or explicitly marked unverified.

## Procedure

1. Read the current-state checkpoint and applicable project, milestone, engineering, RFC, and ADR documents.
2. Verify Git branch, base branch, commit, working tree, remote, and relevant feature-branch state.
3. Verify pull request and CI state through GitHub when required; do not treat a stale checkpoint as live external state.
4. Reconcile milestone status, completed and remaining work, approvals, handoffs, blockers, limitations, and the next authorized action.
5. Update `docs/project/current-state.md` only when the scoped task authorizes a durable checkpoint.
6. Distinguish verified state, user-reported state, stale claims, assumptions, and unavailable checks.

## Expected outputs

A concise context recovery report containing active milestone, verified repository state, applicable decisions, outstanding work, pending approvals, discrepancies, and next authorized action.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include the checkpoint path, evidence sources, state discrepancies, unverified external checks, and next action.

## Verification requirements

Verify that Git state comes from Git, PR/CI state comes from GitHub or is marked unverified, accepted ADRs are distinguished from proposals, and the checkpoint is not used as a substitute for live state.

## Stop conditions

Stop with `BLOCKED` if the active milestone or next authorized action cannot be established safely. Do not infer completion from stale documentation or an unverified merge notification.

## References

- `docs/project/current-state.md`
- `docs/engineering/handoff-protocol.md`
- `docs/engineering/git-workflow.md`
- `docs/engineering/orchestration.md`
