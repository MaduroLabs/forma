# Engineering handoff protocol

Every delegated task has a durable, concise handoff. Use the templates in `docs/engineering/templates/` when the result needs to survive the current turn.

## Assignment fields

Every assignment includes:

- Task ID.
- Assigned agent.
- Objective.
- Scope and explicit non-goals.
- Relevant repository files.
- Applicable approved decisions and proposals.
- Dependencies.
- Expected deliverables.
- Acceptance criteria.
- Allowed write scope.
- Required verification.

## Completion fields

Every completion report includes:

- Task ID and agent identity.
- One state: `COMPLETED`, `NEEDS_REVISION`, `BLOCKED`, or `NEEDS_HUMAN_APPROVAL`.
- Summary.
- Files inspected and files changed.
- Decisions and assumptions.
- Supporting evidence.
- Validation performed and unexecuted checks with reasons.
- Outstanding risks.
- Blocking issues.
- Recommended next action.

Agents must not hide uncertainty or call an incomplete task completed. The coordinator records conflicts and does not silently choose between incompatible recommendations.
