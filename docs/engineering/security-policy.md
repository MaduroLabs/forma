# Security policy

Security is a quality gate for any feature that executes tools, loads skills, handles secrets, accesses files or networks, invokes subprocesses, or moves data to remote inference.

## Required practices

- Model trust boundaries and data flows before granting capability.
- Keep secrets out of source, logs, prompts, reports, and commits.
- Treat skills, prompts, model output, external files, and provider responses as potentially untrusted.
- Make filesystem, network, subprocess, and remote-execution permissions explicit.
- Prefer local execution; require appropriate authorization for remote execution.
- Review dependencies and build scripts for supply-chain risk.
- Classify findings by severity and include evidence, impact, remediation, and residual risk.

Instruction-only restrictions must be labeled as such. Shared credentials or tools are not technical isolation. Never transmit repository secrets or sensitive data to an external research or inference service without explicit authorization.

## Enforcement boundary and blocking rule

The repository does not provide per-agent operating-system isolation. Parent-controlled sandbox, approval, credential, network, and MCP settings are the enforcement boundary. A role description or skill instruction cannot grant or revoke those capabilities.

For a security-sensitive task, the coordinator must record the available parent controls before delegation. If read-only review isolation, credential scope, egress control, or write ownership cannot be established, the task remains `BLOCKED` until the Project Owner authorizes an adequately controlled route. This is a required stop condition, not a waiver.
