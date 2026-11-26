# Agent permissions and enforcement

## Actual Codex behavior

Project custom agents inherit the parent session's permissions, provider, and MCP servers. Their TOML files cannot override the parent sandbox or approval policy. The parent session must set those controls before delegation. The repository `.codex/config.toml` only sets the verified concurrency cap of four.

The custom-agent instructions are behavioral boundaries, not operating-system or credential enforcement. All agents sharing the parent session may have the same underlying credentials and tools. This repository does not claim technical isolation that it cannot verify.

## Security-sensitive delegation preflight

Before delegating work that may encounter secrets, untrusted content, filesystem or network access, subprocesses, cloud execution, external tools, or Git publishing, the coordinator must verify the parent controls for that task:

- Review-only work has a read-only filesystem and no child write ownership.
- Credentials, network access, MCP tools, and external egress are disabled unless explicitly required and authorized.
- Any required write or external operation has a bounded scope and remains under parent approval control.
- The child cannot merge, enable auto-merge, alter protection, or publish to `main`.

If these controls cannot be verified, the task is `BLOCKED`; instruction-only role boundaries are not a substitute for technical isolation. Do not silently downgrade a mandatory security gate.

## Role matrix

| Role class | Intended access | Enforcement status |
| --- | --- | --- |
| Coordinator | Read, plan, delegate, consolidate, prepare branch and PR | Parent sandbox and approval controls; no merge authority by policy |
| Architect/research/DX | Read; write only assigned proposal or documentation files | Write scope is instruction-based |
| Implementation engineers | Write only explicitly assigned files | Parent sandbox plus instruction-based ownership |
| `core-code-reviewer` | Read-only review | Read-only is instruction-based in the current runtime; no per-agent sandbox override is claimed |
| QA/performance/security/release | Read and run safe validation; write only assigned reports or CI files | Parent sandbox and explicit task scope |

## Human boundaries

Never commit secrets, send repository-sensitive data externally, push `main`, force-push, bypass rules, modify protection settings, merge, enable auto-merge, publish releases, or install models without explicit authorization. A role instruction does not grant any of these capabilities.
