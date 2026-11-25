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

Before a commit, inspect `git status`, the complete diff, `git diff --check`, secret-sensitive paths, and the applicable validation evidence. Before opening a pull request, confirm the target branch, intended file list, acceptance criteria, and human approval boundary.
