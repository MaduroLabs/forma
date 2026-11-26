---
name: core-skill-runtime-design
description: Design product-level skill manifests, schemas, discovery, compatibility, permissions, context, and lifecycle independently from Codex engineering skills.
---

## When to use

Use for the future Core product skill runtime. Do not use it to create or modify Codex engineering skills; those live under `.agents/skills/` and follow the Agent Skills format.

## When not to use

Do not use for Codex engineering skill maintenance, generic orchestration, or product-runtime implementation without an approved implementation milestone.

## Required inputs

- Product skill use cases and terminology.
- Manifest, schema, tool, permission, trust, compatibility, and lifecycle requirements.
- Relevant architecture and security decisions.

## Preconditions

- Product-level skills are explicitly in scope for the active milestone.
- Engineering skills and product artifacts are kept in separate locations.

## Procedure

1. Define product skill terminology and distinguish it from Codex development skills.
2. Specify manifest identity, version compatibility, input/output schemas, context injection, tools, permissions, trust, isolation, loading, validation, and lifecycle.
3. Identify model-independent contracts and provider boundaries.
4. Mark security and compatibility decisions that require human approval.
5. Produce a proposal or RFC; do not implement the runtime from a design task without an approved implementation milestone.

## Expected outputs

A product-level skill runtime design with manifest examples, validation rules, permission model, risks, and open questions.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include terminology distinction, proposed manifests/schemas, assumptions, security/compatibility approval questions, files inspected or changed, validation, and next action.

## Verification requirements

Verify that permissions are explicit, untrusted skills are not treated as trusted code, and Codex skill files are not presented as Core product artifacts.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` for permission, trust, isolation, compatibility, or public lifecycle decisions. Stop with `BLOCKED` if the product scope is not authorized.

## References

- `docs/architecture/principles.md`
- `docs/engineering/security-policy.md`
- `docs/rfc/README.md`
