---
name: core-security-review
description: Perform evidence-based security review of Core trust boundaries, permissions, secrets, untrusted content, subprocesses, network, and supply chain.
---

## When to use

Use for security-sensitive design or implementation review.

## When not to use

Do not use to silently change security policy, handle or transmit secrets, or replace the implementation owner.

## Required inputs

- Assets, actors, trust boundaries, entry points, privileged operations, and data flows.
- Relevant design, implementation, dependency, and data-locality evidence.

## Preconditions

- Sensitive data can remain local during the review.
- The parent session has supplied any required sandbox or approval controls.

## Procedure

1. Identify assets, actors, trust boundaries, entry points, privileged operations, and data flows.
2. Analyze prompt injection, untrusted skills and content, secret exposure, filesystem and network access, subprocess execution, dependency supply chain, and local-versus-remote execution.
3. Classify each finding by severity and include evidence, impact, exploit or failure path, remediation, and residual risk.
4. Validate fixes without handling or transmitting secrets.

## Expected outputs

A security report using `docs/engineering/templates/security-finding.md` and a clear gate recommendation.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md` and `docs/engineering/templates/security-finding.md`. Include assets, trust boundaries, findings, severity, evidence, validation, residual risk, blockers, and next action.

## Verification requirements

Verify that policy claims distinguish instruction-only behavior from technical enforcement and that sensitive data stayed local unless explicitly authorized.

## Stop conditions

Stop with `BLOCKED` if required security evidence is unavailable. Stop with `NEEDS_REVISION` for unresolved high-severity findings.

## References

- `docs/engineering/security-policy.md`
- `docs/engineering/templates/security-finding.md`
- `docs/engineering/quality-gates.md`
