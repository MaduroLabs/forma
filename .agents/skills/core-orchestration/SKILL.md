---
name: core-orchestration
description: Coordinate substantive Forma Core engineering work through bounded native subagent delegation and human-gated quality checks.
---

## When to use

Use this skill when the top-level Codex session is coordinating a non-trivial Core task, milestone, review, or research effort. It activates lead behavior in the current session; do not spawn a second coordinator merely to use the skill.

## When not to use

Do not use heavyweight delegation for trivial read-only questions or a one-file change with no material decision. Do not use it to replace context recovery, milestone state ownership, specialist analysis, or Git publishing procedures.

## Required inputs

- Recovered project context and active milestone.
- Objective, scope, non-goals, acceptance criteria, dependencies, and approval gates.
- Agent–Skill Registry and available runtime capabilities.

## Preconditions

- `core-context-management` has reconciled repository state for substantive or resumed work.
- Write ownership is disjoint, or overlapping implementation is serialized.

## Procedure

1. Read `AGENTS.md` and the relevant project, architecture, engineering, and milestone documents.
2. State scope, non-goals, acceptance criteria, dependencies, and approval gates.
3. Choose only the specialist agents needed. Delegate independent tasks with disjoint write scopes and use at most four concurrent subagents unless the Project Owner approves a change.
4. Collect actual subagent results through native Codex mechanisms. If the runtime cannot select named project agents, say so and pass bounded role instructions explicitly; never fabricate delegation.
5. Consolidate common requirements, conflicts, risks, open questions, and evidence. Request human approval before material architecture or policy decisions.
6. Run the applicable quality gates and prepare a handoff or pull request report without merging.

7. Handle child timeout, cancellation, failure, partial, stale, duplicate, and retry results explicitly. Release slots where the runtime permits and never treat an unsuccessful result as completed.

Every assignment and completion report must follow `docs/engineering/handoff-protocol.md`. Keep implementation ownership explicit and never let agents edit the same files concurrently.

## Expected outputs

A coordinator summary with scope, delegated task IDs and real results, decisions and approvals, validation evidence, unresolved risks, and the next authorized action.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md` for assignments and completion receipts. Record task and attempt identities, invocation mode, result state, actual child results, conflicts, approvals, validation, blockers, and next action.

## Verification requirements

Verify that no product implementation was introduced when the task is infrastructure-only, all claims are backed by repository or runtime evidence, runtime limitations are disclosed, and human merge authority is preserved.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` for a pending human decision. Stop with `BLOCKED` when required context, child results, permissions, runtime capabilities, or external state are unavailable. Stop before implementation when a material decision is unresolved and stop before merge in all cases.

## References

- `docs/project/current-state.md`
- `docs/engineering/skill-registry.md`
- `docs/engineering/handoff-protocol.md`
- `docs/engineering/quality-gates.md`
- `docs/engineering/orchestration.md`
