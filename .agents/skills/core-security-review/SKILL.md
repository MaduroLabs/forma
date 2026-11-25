---
name: core-security-review
description: Perform evidence-based security review of Core trust boundaries, permissions, secrets, untrusted content, subprocesses, network, and supply chain.
---

Use for security-sensitive design or implementation review.

Procedure:

1. Identify assets, actors, trust boundaries, entry points, privileged operations, and data flows.
2. Analyze prompt injection, untrusted skills and content, secret exposure, filesystem and network access, subprocess execution, dependency supply chain, and local-versus-remote execution.
3. Classify each finding by severity and include evidence, impact, exploit or failure path, remediation, and residual risk.
4. Validate fixes without handling or transmitting secrets.

Expected output: a security report using `docs/engineering/templates/security-finding.md` and a clear gate recommendation.

Verify that policy claims distinguish instruction-only behavior from technical enforcement and that sensitive data stayed local unless explicitly authorized.
