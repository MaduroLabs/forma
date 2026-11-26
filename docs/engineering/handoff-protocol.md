# Engineering handoff protocol

Every substantive delegated task has a concise handoff. Use the templates in `docs/engineering/templates/` when the result needs to survive the current turn. Trivial tasks may use a compact form containing the same essential fields.

## Assignment fields

Every assignment includes:

- Task ID.
- Milestone ID.
- Assigned agent.
- Invocation mode: named custom agent, generic native subagent, or sequential fallback.
- Objective.
- Scope and explicit non-goals.
- Relevant repository files.
- Applicable approved decisions and proposals.
- Dependencies.
- Expected deliverables.
- Acceptance criteria.
- Allowed write scope.
- Required verification.
- Stop conditions.

Security-sensitive assignments additionally record the parent-control preflight: filesystem mode and write scope, credential availability, network and MCP access, external egress, approval policy, and Git-publishing controls. If any required control is unavailable, the assignment is `BLOCKED`.

## Completion fields

Every completion report includes:

- Task ID, attempt ID when applicable, and agent or assigned-role identity.
- Invocation mode.
- One state: `COMPLETED`, `NEEDS_REVISION`, `BLOCKED`, `NEEDS_HUMAN_APPROVAL`, `CANCELLED`, or `TIMED_OUT`.
- Summary.
- Files inspected and files changed.
- Decisions and assumptions.
- Supporting evidence.
- Validation performed and unexecuted checks with reasons.
- Outstanding risks.
- Blocking issues.
- Recommended next action.

Security-sensitive completion reports repeat the parent-control preflight, identify which controls were technically enforced versus instruction-only, and record any required Project Owner risk acceptance.

Partial results may accompany an unsuccessful state but must not be reported as `COMPLETED`. A timeout, cancellation, stale result, duplicate result, or failed retry must remain visible. The coordinator records conflicts and does not silently choose between incompatible recommendations.

## Failure-state mapping

- Runtime, permission, dependency, or external-state failure: `BLOCKED`.
- Failed acceptance criteria or invalid/incomplete deliverable: `NEEDS_REVISION`.
- Pending Project Owner decision: `NEEDS_HUMAN_APPROVAL`.
- Native execution timeout: `TIMED_OUT`.
- Explicitly stopped task: `CANCELLED`.

Preserve the task ID, attempt ID, failure reason, and partial-result status in every unsuccessful handoff.

Agents must not hide uncertainty or call an incomplete task completed. The coordinator records conflicts and does not silently choose between incompatible recommendations.
