---
name: core-model-routing
description: Analyze capability-based model discovery, hardware-aware resource estimation, and routing decisions without coupling workflows to providers.
---

## When to use

Use for model selection, routing policy, discovery metadata, hardware suitability, resource estimation, or fallback analysis.

## When not to use

Do not use to define provider adapter contracts, implement providers, or encode hardware assumptions in workflow definitions.

## Required inputs

- Requested capability and execution constraints.
- Approved capability/provider contracts, when available.
- Discovery metadata, locality, availability, resource, latency, privacy, and failure signals.

## Preconditions

- The routing question is separated from model-family and provider implementation details.
- Any quantitative performance or hardware claim has evidence or is labeled as an assumption.

## Procedure

1. Define the requested capability and execution constraints separately from model names.
2. Identify descriptor fields, confidence, availability, provider-reported resource facts, routing estimates, locality, latency, cost, privacy, and failure signals.
3. Compare deterministic, policy-driven, and adaptive routing alternatives with observable decision reasons.
4. Keep hardware detection and provider knowledge behind replaceable boundaries. Providers expose observed or declared facts; routing owns estimation policy, suitability interpretation, and route selection.
5. State fallback, cancellation, and retry behavior and list approval-required policy choices.

## Expected outputs

A routing analysis or proposal with inputs, decision rules, evidence, failure cases, open questions, and validation criteria.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include capability inputs, route rules, provider-contract dependencies, evidence, fallback semantics, risks, approval questions, and next action.

## Verification requirements

Verify that routing is capability-based, workflows do not encode hardware assumptions, route decisions are observable, and no performance or compatibility claim lacks evidence.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` if routing would define public capability semantics, remote-execution policy, or compatibility guarantees not already approved.

## References

- `docs/architecture/principles.md`
- `docs/engineering/skill-registry.md`
- `.agents/skills/core-provider-design/SKILL.md`
