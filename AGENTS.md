# Forma Core engineering policy

Forma is a modular, model-agnostic, local-first AI workflow engine intended to become a reusable Rust Core. This repository is independent of desktop UI, marketing logic, specific model families, providers, operating systems, and company workflows.

## Working agreements

- Read the relevant files under `docs/project/`, `docs/architecture/`, `docs/adr/`, `docs/rfc/`, and `docs/engineering/` for the task at hand. These documents distinguish approved decisions, proposals, open questions, facts, assumptions, and limitations.
- For substantive work, use the `core-orchestration` skill to activate the top-level coordinator behavior in the current session. Delegate only bounded, independent tasks through the native Codex subagent tools when available; do not add a nested coordinator layer.
- Discover specialist custom agents under `.codex/agents/` and shared skills under `.agents/skills/`. Agent instructions describe responsibilities, not technical permission enforcement. The parent session controls sandbox and approvals.
- Every delegated task and completion report follows `docs/engineering/handoff-protocol.md`.
- Material public API, persistence, provider, security, compatibility, or breaking-change decisions require Project Owner approval and an RFC or ADR as appropriate. Do not invent approved decisions.
- Keep changes scoped to the task. Do not implement the Core product during A0. Do not add UI or marketing-specific agents.
- Run applicable validation and disclose commands that were not run. Do not require Cargo tests when no Rust project exists.
- Never commit secrets. Never push directly to `main`, force-push, bypass rulesets, merge pull requests, enable auto-merge, publish releases, or modify repository protection without explicit authorization.

## Documentation hierarchy

`AGENTS.md` owns durable repository behavior. `docs/project/` owns mission and scope. `docs/architecture/` owns principles. `docs/adr/` records approved decisions; `docs/rfc/` records proposals. `docs/engineering/` owns operating procedures, handoffs, quality gates, and templates. `docs/milestones/` owns milestone evidence.

## Definition of Done

A change is done only when scope and approvals are clear, implementation and documentation match approved requirements, applicable verification passes or is disclosed, independent review is complete when required, security and performance concerns are addressed when relevant, and the final diff contains only intended changes. Human merge authority remains outside the agent team.
