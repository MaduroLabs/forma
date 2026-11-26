# A0.2/A0.3 manual pull-request fallback

This fallback is intentionally independent of any future bookkeeping commit. Obtain the live branch HEAD from Git or GitHub immediately before creating the pull request; do not add that transient SHA to this document merely to synchronize the document with itself.

## Repository and branches

- Repository: `MaduroLabs/forma`
- Head branch: `chore/a0-core-agent-infrastructure`
- Base branch: `main`
- Comparison URL: https://github.com/MaduroLabs/forma/compare/main...chore/a0-core-agent-infrastructure
- Baseline implementation commit: `f7156b6e84f850b34d820fc220bad69c0c42b332`
- Reviewed pre-remediation tree: `f1f9d04b53c7e64f60346a7936ef9697dcb79357`
- Final live HEAD: verify separately at delivery

## Exact title

`chore: finalize A0 engineering infrastructure remediation`

## Complete pull-request description

```markdown
## Summary

- Reconcile A0/A0.2 delivery evidence without self-referential commit bookkeeping.
- Add concise durable review and validation evidence under `docs/milestones/evidence/A0.2/`.
- Add explicit parent-control preflight and blocking rules for security-sensitive delegation.
- Complete the manual PR fallback and post-remediation readiness documentation.

## Scope

This pull request is limited to Forma Core engineering infrastructure and documentation. It introduces no Rust product implementation, provider integration, runtime, storage engine, CI workflow, or M0 work.

## Evidence

- 13 custom agents and 21 engineering skills remain present.
- Skill contracts, registry mappings, documentation references, and product-scope scans are recorded in `docs/milestones/evidence/A0.2/validation-summary.md`.
- Fresh independent review and security evidence are recorded under `docs/milestones/evidence/A0.2/`.
- The reviewed implementation baseline is `f7156b6e84f850b34d820fc220bad69c0c42b332`; the final head commit is verified live at delivery.

## Known limitations

- Named custom-agent selection is unavailable in the current native runtime; generic native fallback is explicitly disclosed.
- Agent role restrictions remain instruction-based unless parent runtime controls technically enforce them.
- Security-sensitive tasks are blocked when parent sandbox, credential, egress, or write-ownership controls cannot be verified.
- No Cargo tests apply because no Rust product manifest exists.

## Review boundary

Human merge authority remains outside the agent team. Please review the evidence and approve or request changes; do not infer milestone completion from PR creation alone.
```

## Manual next action

1. Read the live head SHA from GitHub or the pushed remote branch.
2. Search for an existing pull request from `chore/a0-core-agent-infrastructure` to `main`; update and verify it if one exists, and do not create a duplicate.
3. If no PR exists, open one from `chore/a0-core-agent-infrastructure` to `main` using the exact title, description, and comparison URL above.
4. Verify the PR number, head SHA, base branch, and applicable checks.
5. Stop for Project Owner review; do not merge or begin M0.
