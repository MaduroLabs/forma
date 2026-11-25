---
name: core-model-routing
description: Analyze capability-based model discovery, hardware-aware resource estimation, and routing decisions without coupling workflows to providers.
---

Use for model selection, routing policy, discovery metadata, hardware suitability, resource estimation, or fallback analysis.

Procedure:

1. Define the requested capability and execution constraints separately from model names.
2. Identify descriptor fields, confidence, availability, resource estimates, locality, latency, cost, privacy, and failure signals.
3. Compare deterministic, policy-driven, and adaptive routing alternatives with observable decision reasons.
4. Keep hardware detection and provider knowledge behind replaceable boundaries.
5. State fallback, cancellation, and retry behavior and list approval-required policy choices.

Expected output: a routing analysis or proposal with inputs, decision rules, evidence, failure cases, open questions, and validation criteria.

Verify that routing is capability-based, workflow definitions do not encode hardware assumptions, and no performance claim lacks measurement.
