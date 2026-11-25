---
name: core-orchestration
description: Coordinate substantive Forma Core engineering work through bounded native subagent delegation and human-gated quality checks.
---

Use this skill when the top-level Codex session is coordinating a non-trivial Core task, milestone, review, or research effort. It activates lead behavior in the current session; do not spawn a second coordinator merely to use the skill.

Procedure:

1. Read `AGENTS.md` and the relevant project, architecture, engineering, and milestone documents.
2. State scope, non-goals, acceptance criteria, dependencies, and approval gates.
3. Choose only the specialist agents needed. Delegate independent tasks with disjoint write scopes and use at most four concurrent subagents unless the Project Owner approves a change.
4. Collect actual subagent results through native Codex mechanisms. If the runtime cannot select named project agents, say so and pass bounded role instructions explicitly; never fabricate delegation.
5. Consolidate common requirements, conflicts, risks, open questions, and evidence. Request human approval before material architecture or policy decisions.
6. Run the applicable quality gates and prepare a handoff or pull request report without merging.

Every assignment and completion report must follow `docs/engineering/handoff-protocol.md`. Keep implementation ownership explicit and never let agents edit the same files concurrently.

Expected output: a coordinator summary with scope, delegated task IDs and real results, decisions and approvals, validation evidence, unresolved risks, and the next authorized action.

Verify that no product implementation was introduced when the task is infrastructure-only, all claims are backed by repository or runtime evidence, and human merge authority is preserved.
