---
name: core-skill-runtime-design
description: Design product-level skill manifests, schemas, discovery, compatibility, permissions, context, and lifecycle independently from Codex engineering skills.
---

Use for the future Core product skill runtime. Do not use it to create or modify Codex engineering skills; those live under `.agents/skills/` and follow the Agent Skills format.

Procedure:

1. Define product skill terminology and distinguish it from Codex development skills.
2. Specify manifest identity, version compatibility, input/output schemas, context injection, tools, permissions, trust, isolation, loading, validation, and lifecycle.
3. Identify model-independent contracts and provider boundaries.
4. Mark security and compatibility decisions that require human approval.
5. Produce a proposal or RFC; do not implement the runtime during A0.

Expected output: a product-level skill runtime design with manifest examples, validation rules, permission model, risks, and open questions.

Verify that permissions are explicit, untrusted skills are not treated as trusted code, and Codex skill files are not presented as Core product artifacts.
