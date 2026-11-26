# A0.3 security review evidence

- Task ID: `A0.3-SECURITY-001`
- Attempts recorded: `attempt-1` (initial blocked review) and `attempt-2` (final controlled snapshot review)
- Assigned role: Security Engineer
- Invocation mode: `GENERIC_NATIVE_SUBAGENT`; named custom-agent selection unavailable
- Scope: parent-controlled permissions, reviewer restrictions, credentials, secrets, filesystem/network, tools, untrusted content, write ownership, and Git publishing
- Reviewed baseline: `f1f9d04b53c7e64f60346a7936ef9697dcb79357` plus A0.3 documentation changes

## Final gate result

`PASS` for the controlled A0.3 review snapshot. The snapshot was technically read-only, no secrets or external calls were used, and no files were changed by the reviewer. This does not generalize to future tasks without a fresh parent-control preflight.

## Initial result

`BLOCKED` pending verification of the parent-control preflight and durable evidence artifacts. The initial review was run against the managed read-only worktree before these artifacts existed, so it is not treated as final approval.

## Risk record

### High residual risk — no per-agent technical isolation

- Evidence: `docs/engineering/agent-permissions.md` and `docs/engineering/security-policy.md` state that custom agents inherit parent sandbox, credentials, provider, and MCP access.
- Impact: instruction-only read-only or write-scope boundaries cannot prevent a child from accessing capabilities granted by the parent.
- Mitigation: parent preflight is mandatory; security-sensitive tasks are `BLOCKED` unless filesystem isolation, credential scope, egress, tool access, approval policy, and write ownership are verified.
- Residual risk: the repository cannot create per-agent OS or credential isolation.
- Project Owner acceptance: required before any security-sensitive task proceeds without those controls. The acceptance must name the task, data exposure, permitted capabilities, duration, and rollback/containment plan.

## Technical versus behavioral controls

- Technically enforced by the environment: restricted parent filesystem roots, approval-controlled external operations, and the top-level coordinator’s commit/push/PR authority for this run.
- Instruction-only: child role boundaries, no-write instructions, no-secret handling, no external calls, and no Git publishing.
- Not available in the current runtime: per-child credential isolation, per-child MCP denial, and authenticated named-agent identity.

## Final review receipt

- Task ID: `A0.3-SECURITY-001`
- Attempt ID: `A0.3-SECURITY-001/attempt-2`
- Invocation mode: `GENERIC_NATIVE_SUBAGENT`
- Completion state: `COMPLETED`
- Gate result: `PASS` for the read-only snapshot
- Snapshot controls: directories `555`, files `444`; no child write ownership; no secrets supplied; no external calls made
- Findings: no task-specific blocker; residual no-per-agent technical isolation remains documented above
- Unexecuted: live GitHub/PR/CI, named-agent selection, and full TOML parsing
- Next action: retain the blocking rule for future tasks and request Project Owner acceptance before security-sensitive work without equivalent controls
