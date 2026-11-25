---
name: core-technical-research
description: Research AI runtimes, model capabilities, hardware support, open-source approaches, benchmarks, and licensing for Forma Core decisions.
---

## When to use

Use when a Core decision needs current external technical evidence. Prefer official runtime documentation, source repositories, papers, specifications, and published benchmark methodology.

## When not to use

Do not use to silently finalize architecture, invent benchmarks, or transmit repository-sensitive content to external services.

## Required inputs

- Research question and decision context.
- Comparison dimensions, source requirements, and date/version expectations.

## Preconditions

- The question is open and does not presuppose a preferred answer.
- External research can be conducted without exposing sensitive repository data.

## Procedure

1. Define the research question and the decisions it may inform without presupposing an answer.
2. Search primary sources first and record URL, version, date checked, and evidence.
3. Separate verified facts, assumptions, hypotheses, and unverified claims.
4. Compare alternatives using the same dimensions: capability, hardware, lifecycle, performance evidence, licensing, portability, and operational risk.
5. State what the evidence cannot establish and which questions need experiments or Project Owner approval.

## Expected outputs

A concise research report with an evidence table, comparison, uncertainty, implications for Core, and recommended next step.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include question, sources, evidence table, versions/dates, verified facts, assumptions, uncertainty, limitations, implications, and next action.

## Verification requirements

Verify that no benchmark or capability is invented, no sensitive repository content is transmitted, primary sources are preferred, and the report does not silently finalize architecture.

## Stop conditions

Stop with `BLOCKED` if current primary evidence cannot be obtained. Stop with `NEEDS_HUMAN_APPROVAL` when research only supports a material architectural choice rather than making it.

## References

- `docs/architecture/principles.md`
- `docs/engineering/security-policy.md`
- `docs/engineering/handoff-protocol.md`
