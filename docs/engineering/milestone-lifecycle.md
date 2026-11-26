# Milestone lifecycle

Milestone state describes delivery evidence. It does not approve product architecture, replace GitHub state, or authorize the next milestone.

## States

`PROPOSED`, `AWAITING_APPROVAL`, `APPROVED`, `IN_PROGRESS`, `IN_REVIEW`, `READY_FOR_PR`, `PR_OPEN`, `MERGED`, `COMPLETED`, `BLOCKED`, `NEEDS_REVISION`, and `CANCELLED`.

## Legal transitions

| From | To | Required evidence | Responsible role |
| --- | --- | --- | --- |
| `PROPOSED` | `AWAITING_APPROVAL` | Scope contains a material decision or explicit approval request | Coordinator |
| `PROPOSED` | `APPROVED` | Project Owner explicitly approves the defined scope; no separate material decision gate is required | Project Owner / coordinator records it |
| `AWAITING_APPROVAL` | `APPROVED` | Explicit Project Owner approval and conditions | Project Owner / coordinator records it |
| `AWAITING_APPROVAL` | `NEEDS_REVISION` | Owner requests changed scope or evidence | Coordinator |
| `AWAITING_APPROVAL` | `CANCELLED` | Explicit cancellation | Project Owner |
| `APPROVED` | `IN_PROGRESS` | Context recovered, branch/work ownership established, and acceptance criteria available | Coordinator |
| `IN_PROGRESS` | `IN_REVIEW` | Implementation scope complete and validation evidence available | Coordinator |
| `IN_PROGRESS` | `BLOCKED` | Unresolved blocker or unavailable required dependency | Coordinator |
| `IN_PROGRESS` | `NEEDS_REVISION` | Work does not satisfy scope or acceptance criteria | Coordinator / reviewer |
| `IN_PROGRESS` | `CANCELLED` | Explicit cancellation | Project Owner |
| `IN_REVIEW` | `READY_FOR_PR` | Applicable review and quality gates pass; diff is scoped | Coordinator |
| `IN_REVIEW` | `NEEDS_REVISION` | Blocking review or validation finding | Coordinator |
| `IN_REVIEW` | `BLOCKED` | Required external state or approval is unavailable | Coordinator |
| `READY_FOR_PR` | `PR_OPEN` | Commit pushed and PR identity/target verified | Coordinator |
| `READY_FOR_PR` | `BLOCKED` | Push or PR creation is blocked; manual fallback recorded | Coordinator |
| `PR_OPEN` | `MERGED` | GitHub independently verifies merge into `main` | Project Owner / coordinator records it |
| `PR_OPEN` | `NEEDS_REVISION` | Review requests changes | Coordinator |
| `PR_OPEN` | `BLOCKED` | PR/CI state cannot be verified or required external action is blocked | Coordinator |
| `MERGED` | `COMPLETED` | Acceptance criteria reconciled, closeout recorded, risks carried forward | Coordinator |
| `MERGED` | `NEEDS_REVISION` | Merged result does not satisfy milestone acceptance criteria | Coordinator / Project Owner |
| `MERGED` | `BLOCKED` | Merge is reported but expected changes cannot be verified | Coordinator |
| `BLOCKED` | `IN_PROGRESS` | Blocker resolved and context re-recovered | Coordinator |
| `BLOCKED` | `NEEDS_REVISION` | Scope or plan must change | Coordinator / Project Owner |
| `BLOCKED` | `CANCELLED` | Explicit cancellation | Project Owner |
| `NEEDS_REVISION` | `IN_PROGRESS` | Revised scope or correction is authorized | Coordinator |
| `NEEDS_REVISION` | `CANCELLED` | Explicit cancellation | Project Owner |

`COMPLETED` and `CANCELLED` are terminal for that milestone record. A later milestone must be proposed separately.

## Completion semantics

- Implementation complete means assigned changes exist.
- Validation complete means applicable checks have evidence or documented `NOT_RUN`/`BLOCKED` results.
- `READY_FOR_PR` means the branch is ready for publishing; it is not a PR.
- `PR_OPEN` means GitHub verified the PR identity and target.
- `MERGED` means GitHub verified the changes landed on `main`.
- `COMPLETED` means milestone acceptance criteria and closeout evidence are reconciled.

Do not infer a later state from an earlier state. A successful push is not a merge, and a merged PR is not automatically a completed milestone.

## Required milestone record

Use `docs/engineering/templates/milestone-completion.md` for closeout and include milestone identifier, objective, scope, non-goals, dependencies, approval status, acceptance criteria, assignments, validation, completion evidence, carry-forward risks, limitations, and next authorized action.
