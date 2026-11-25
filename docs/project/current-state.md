# Current project state

This is a compact navigation checkpoint, not a roadmap, issue tracker, Git history, or agent transcript. Live GitHub state must be verified externally.

## Current milestone

- Milestone: `A0.2 — Forma Core Engineering Infrastructure Refinement`
- Status: `READY_FOR_PR`
- Scope: refine Codex engineering infrastructure only; no Forma Core product implementation
- Branch: `chore/a0-core-agent-infrastructure`
- Base branch: `main`

## Decisions applicable to this milestone

- Retain 13 custom agents.
- Finalize exactly 21 engineering skills: the existing 18 plus context management, milestone management, and persistence design.
- Use `core-orchestration` as the primary engineering entry point; do not create `core-task-execution`.
- Use a Markdown Agent–Skill Registry as repository-level convention.
- Standardize context, milestone, handoff, RFC/ADR, quality-gate, Git, and post-merge procedures.
- Do not assume Tokio, SQLite, or another runtime/storage engine.
- Generic native subagent fallback is allowed when named-agent selection is unavailable, with explicit disclosure.

## Completed work

- A0 infrastructure exists on the current branch.
- A0.1 audit identified mapping, lifecycle, handoff, persistence, and runtime-verification gaps.

## Remaining work

- Apply and validate A0.2 refinements. (complete)
- Obtain independent review. (complete; named-agent selection remains unverified)
- Commit and push the intended changes.
- Create or update the pull request targeting `main`.
- Stop for Project Owner merge approval.

## Pending approvals

- No new product architecture decision is requested by A0.2.
- Future product persistence, provider, workflow, API, runtime, and storage-engine decisions remain subject to the RFC → human approval → accepted ADR lifecycle.

## Known limitations

- The current runtime may delegate generic native subagents without proving named `.codex/agents/*.toml` selection.
- Agent instructions are behavioral boundaries; shared credentials and parent tools are not technical role isolation.
- GitHub state is live external state and must not be inferred from this checkpoint.
- No Cargo tests apply because no Rust product manifest exists.

## References

- [A0 milestone](../milestones/A0.md)
- [A0.2 milestone](../milestones/A0.2.md)
- [Skill registry](../engineering/skill-registry.md)
- [Orchestration protocol](../engineering/orchestration.md)
- [Handoff protocol](../engineering/handoff-protocol.md)

## Last verification

- Checkpoint purpose: A0.2 implementation start.
- Verified local branch and working tree before edits.
- Verified no existing pull request for `chore/a0-core-agent-infrastructure` through the available GitHub integration.
- Local GitHub SSH access was unavailable; push and final PR state require later verification.

## Next authorized action

Complete the approved A0.2 refinement, validate it, and prepare the existing A0 branch for its pull request. Do not begin M0.
