# Forma Core engineering policy

Forma is a modular, model-agnostic, local-first AI workflow engine intended to become a reusable Rust Core. This repository is independent of desktop UI, marketing logic, specific model families, providers, operating systems, and company workflows.

## Working agreements

- Read the relevant files under `docs/project/`, `docs/architecture/`, `docs/adr/`, `docs/rfc/`, and `docs/engineering/` for the task at hand. These documents distinguish approved decisions, proposals, open questions, facts, assumptions, and limitations.
- For substantive work, use `core-context-management` first, then `core-orchestration` as the primary engineering entry point. Consult `docs/engineering/skill-registry.md` and load only the relevant specialist skills; do not add a nested coordinator layer.
- Discover specialist custom agents under `.codex/agents/` and shared skills under `.agents/skills/`. The registry is a repository convention, not proof of automatic native activation. Agent instructions describe responsibilities, not technical permission enforcement. The parent session controls sandbox and approvals.
- Use `core-milestone-management` for milestone state and `core-git-workflow` for branch, commit, push, PR, and post-merge delivery. Do not conflate implementation completion, PR creation, merge, or milestone completion.
- Every delegated task and completion report follows `docs/engineering/handoff-protocol.md`.
- Material public API, persistence, provider, security, compatibility, or breaking-change decisions require Project Owner approval and an RFC or ADR as appropriate. Do not invent approved decisions.
- Keep changes scoped to the active milestone. Do not implement product functionality when the active milestone excludes it. Do not add UI or marketing-specific agents.
- Run applicable validation and disclose commands that were not run. Do not require Cargo tests when no Rust project exists.
- Never commit secrets. Never push directly to `main`, force-push, bypass rulesets, merge pull requests, enable auto-merge, publish releases, or modify repository protection without explicit authorization.

## Documentation hierarchy

`AGENTS.md` owns durable repository behavior. `docs/project/` owns mission, scope, and the compact current-state checkpoint. `docs/architecture/` owns principles. `docs/adr/` records approved decisions; `docs/rfc/` records proposals. `docs/engineering/` owns the Agent–Skill Registry, lifecycle, operating procedures, handoffs, quality gates, and templates. `docs/milestones/` owns milestone evidence.

Codex engineering skills under `.agents/skills/` are development procedures. They are distinct from future Forma Core product-level skills designed by `core-skill-runtime-design`.

The authoritative architecture lifecycle is: architecture analysis → proposed RFC → explicit Project Owner approval → accepted ADR → authorized implementation. An RFC or agent consensus never substitutes for approval.

## Definition of Done

A change is done only when scope and approvals are clear, implementation and documentation match approved requirements, applicable verification passes or is disclosed, independent review is complete when required, mandatory risk gates are addressed, handoffs are complete, and the final diff contains only intended changes. Human merge authority remains outside the agent team. A pushed branch, open PR, or merged PR is not by itself proof of milestone completion.
