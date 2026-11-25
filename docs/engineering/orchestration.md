# Orchestration protocol

## Runtime model

The top-level Codex session is the Project Owner-facing coordinator. For substantive work it adopts the `core-orchestration` skill and performs the Core Engineering Lead function directly. The custom `core-engineering-lead` role is available for planning and coordination when the host can select named custom agents; it is not an additional mandatory layer.

Codex project custom agents are standalone TOML files in `.codex/agents/`. Repository skills are discovered under `.agents/skills/`. Project configuration is in `.codex/config.toml` and caps open spawned-agent threads at four.

The verified current Codex CLI is `0.171.0`. Official documentation identifies native `spawn_agent`, `send_input`, `resume_agent`, `wait_agent`, and `close_agent` collaboration tools, and project custom agents under `.codex/agents/`. The local tool surface must still be checked at runtime because tool schemas and feature flags can change.

References: [Codex subagents](https://developers.openai.com/codex/subagents), [Codex configuration reference](https://developers.openai.com/codex/config-reference), and [Codex skills](https://developers.openai.com/codex/skills).

## Lifecycle

1. Recover project context with `core-context-management`.
2. Read the active milestone and classify the task.
3. Define acceptance criteria, dependencies, write ownership, and approval gates.
4. Delegate independent research or analysis where it materially improves quality.
5. Consolidate alternatives and request human approval for material decisions.
6. Create an implementation plan and assign disjoint ownership.
7. Implement within scope.
8. Run independent QA and code review; add mandatory security, performance, cross-platform, or release review according to `quality-gates.md`.
9. Resolve blocking findings and run final validation.
10. Use `core-git-workflow` to commit, push, and prepare or update a PR targeting `main`.
11. Stop and wait for explicit human merge approval.
12. After a reported merge, re-verify GitHub state, synchronize `main`, close the milestone, and stop unless further work is explicitly authorized.

## Parallel execution

Parallelize independent research and reviews. Serialize implementation when ownership isolation is unavailable. Never let two agents edit the same files concurrently. Parent-mediated communication is the supported coordination pattern; repository handoff artifacts may preserve results between sessions.

## Child lifecycle

Each delegated task has a task ID and, when retried, an attempt ID. Record invocation mode, role instructions, write ownership, acceptance criteria, and required verification. Results use `COMPLETED`, `NEEDS_REVISION`, `BLOCKED`, `NEEDS_HUMAN_APPROVAL`, `CANCELLED`, or `TIMED_OUT`.

Timeouts, cancellations, failures, partial results, stale results, duplicate results, and retries are not successful completion. Retry only safe, apparently recoverable operations, with bounded attempts. Reconcile result identity before consolidation and release execution slots when the runtime permits.

## Runtime limitation handling

If the current native spawn schema cannot select a named `agent_type`, do not claim a custom TOML was applied. Run a bounded generic subagent exercise with the role instructions in the task message if authorized, record the actual tool call and result, and mark named-agent invocation as unverified. Use the manual procedure in `docs/milestones/A0.md` for later validation.
