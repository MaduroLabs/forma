# Git and pull request workflow

This repository uses trunk-based development. `main` is the protected primary branch. Every milestone or engineering task uses a dedicated branch and pull requests target `main` directly. Prefer squash merging.

## Rules

- Start from the latest `main` after a read-only status and remote check.
- Preserve unrelated user changes; never overwrite, discard, or silently include them.
- Never push directly to `main` or force-push it.
- Never bypass rulesets or modify repository protection without authorization.
- Keep implementation ownership and commits scoped.
- Only the top-level coordinator prepares the final branch, commit, push, and pull request.
- Never merge, enable auto-merge, or publish a release.

## Handoff checks

Before a commit, inspect `git status`, the complete diff, `git diff --check`, secret-sensitive paths, and applicable validation evidence. Record the base SHA and final commit SHA. Before opening a pull request, confirm the target branch, head branch, existing PR state, intended file list, acceptance criteria, and human approval boundary.

## Delivery evidence semantics

- Record these identities separately: implementation commit, reviewed commit or tree, last verified remote commit, and live branch HEAD.
- Git and GitHub are authoritative for live branch and pull-request state. A checkpoint is historical evidence and must not be treated as live state.
- Do not make a bookkeeping commit solely to replace a transient live HEAD or PR-state claim. Report that state from Git or GitHub at delivery time.
- Do not make a committed document claim the SHA of the commit that would contain that same document. Record the reviewed tree and the verification time or commit instead.

## Delivery entry point

1. Inspect local and remote state and preserve unrelated changes.
2. Fetch `origin` when available and safely reconcile the latest `origin/main`.
3. Create or resume the authorized feature branch and record its base SHA.
4. Run applicable quality gates, inspect the complete diff, and commit only intended changes.
5. Push the dedicated branch and verify the remote head.
6. Check for an existing PR before creating one. Never create a duplicate.
7. Prefer authenticated GitHub CLI or an authorized GitHub integration. If unavailable, provide a comparison URL, complete title/body, head/base branches, reviewed implementation identity, validation evidence, known limitations, and exact manual action. Obtain live HEAD separately when delivering the report.
8. Verify PR identity and target when possible. Do not claim a PR exists without verification.
9. Stop before merge.

## Post-merge entry point

When the Project Owner reports a merge, verify the PR and merge state, fetch `origin`, confirm expected changes in `origin/main`, safely synchronize local `main`, reconcile milestone acceptance criteria, record closeout, and stop unless further work is explicitly authorized. Squash merging may change the commit SHA; the expected tree, not the feature commit identity alone, is the merge evidence.

Do not create bookkeeping commits solely for transient PR state. If live state cannot be verified, label it user-reported or unverified.
