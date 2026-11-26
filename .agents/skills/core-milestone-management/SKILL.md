---
name: core-milestone-management
description: Manage Forma Core milestone scope, approvals, evidence, lifecycle transitions, completion, and carry-forward work.
---

## When to use

Use when proposing, approving, starting, reviewing, delivering, closing, blocking, revising, cancelling, or resuming a Core milestone.

## When not to use

Do not use for subagent delegation, context recovery, implementation ownership, or Git publishing. Use `core-orchestration`, `core-context-management`, and `core-git-workflow` for those responsibilities.

## Required inputs

- Milestone identifier, objective, scope, non-goals, dependencies, and acceptance criteria.
- Approval state, task assignments, validation requirements, and existing milestone evidence.
- Current repository and pull request state when delivery or resumption is involved.

## Preconditions

- The milestone record has one authoritative location under `docs/milestones/`.
- Material decisions are linked to RFC/ADR evidence and are not inferred from agent consensus.

## Procedure

1. Create or read the milestone record and classify its current lifecycle state.
2. Validate scope, non-goals, dependencies, approval requirements, task ownership, and acceptance criteria.
3. Apply only legal state transitions and record the prerequisite evidence and responsible role.
4. Distinguish implementation complete, validation complete, ready for PR, PR opened, PR merged, and milestone completed.
5. After a verified merge, reconcile acceptance criteria, unresolved risks, deferred work, and the next proposed milestone.
6. Stop after closeout unless the Project Owner explicitly authorizes the next milestone.

## Lifecycle states

`PROPOSED`, `AWAITING_APPROVAL`, `APPROVED`, `IN_PROGRESS`, `IN_REVIEW`, `READY_FOR_PR`, `PR_OPEN`, `MERGED`, `COMPLETED`, `BLOCKED`, `NEEDS_REVISION`, and `CANCELLED`.

Allowed transitions and evidence are defined in `docs/engineering/milestone-lifecycle.md`.

## Expected outputs

A milestone status update or completion report containing state, evidence, acceptance-criteria result, approvals, unresolved risks, carry-forward work, and next authorized action.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md` and `docs/engineering/templates/milestone-completion.md`. Include milestone state, transition evidence, task status, validation, blockers, risks, and next action.

## Verification requirements

Verify that transitions are legal, approval is explicit, PR creation is not treated as merge, merge is independently verified, and completion is not claimed while required evidence is missing.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` for an unapproved milestone or material decision. Stop with `BLOCKED` when required evidence or external state is unavailable. Do not automatically implement a subsequent milestone.

## References

- `docs/engineering/milestone-lifecycle.md`
- `docs/project/current-state.md`
- `docs/engineering/handoff-protocol.md`
- `docs/engineering/git-workflow.md`
