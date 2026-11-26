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
- A0.3 remediation, fresh review, and evidence recording are complete in the reviewed tree.
- Commit and push this scoped remediation to the existing A0 branch.
- Create or update one pull request targeting `main` using the documented fallback, then verify its identity and target.
- Stop for Project Owner merge approval after PR verification.

## Pending approvals

- No new product architecture decision is requested by A0.2.
- Future product persistence, provider, workflow, API, runtime, and storage-engine decisions remain subject to the RFC → human approval → accepted ADR lifecycle.

## Known limitations

- The current runtime may delegate generic native subagents without proving named `.codex/agents/*.toml` selection.
- Agent instructions are behavioral boundaries; shared credentials and parent tools are not technical role isolation. Security-sensitive tasks are blocked when parent isolation cannot be verified.
- GitHub state is live external state and must not be inferred from this checkpoint.
- No Cargo tests apply because no Rust product manifest exists.

## References

- [A0 milestone](../milestones/A0.md)
- [A0.2 milestone](../milestones/A0.2.md)
- [Skill registry](../engineering/skill-registry.md)
- [Orchestration protocol](../engineering/orchestration.md)
- [Handoff protocol](../engineering/handoff-protocol.md)

## Last verification

- Checkpoint purpose: A0.3 remediation handoff.
- Implementation commit: `f7156b6e84f850b34d820fc220bad69c0c42b332`.
- Reviewed commit/tree: `f1f9d04b53c7e64f60346a7936ef9697dcb79357`.
- Last verified remote commit recorded by the prior handoff: `f1f9d04b53c7e64f60346a7936ef9697dcb79357` (historical).
- Live branch HEAD: authoritative Git/GitHub state; obtain separately at delivery and do not chase it with bookkeeping commits.
- Base branch last verified by the prior handoff: `fd537b9bacc8c3973f567078d26fcd20b236b229`.
- Verified no pull request exists for `chore/a0-core-agent-infrastructure`.
- PR creation returned HTTP 403 `Resource not accessible by integration`; implementation is published but PR creation is externally blocked.

## Next authorized action

Commit and push the scoped A0.3 remediation to the existing branch, then create the pull request through an authorized GitHub-capable route or use [`docs/milestones/evidence/A0.2/pr-fallback.md`](../milestones/evidence/A0.2/pr-fallback.md). Obtain live HEAD separately, verify PR identity and target, then stop for Project Owner review. Do not begin M0.
