---
name: core-adr-authoring
description: Record approved Forma Core architecture decisions with context, consequences, and traceable evidence.
---

## When to use

Use only after the Project Owner has approved a material decision and its originating RFC is explicitly `APPROVED`.

## When not to use

Do not use for an unapproved proposal, an implementation plan, or a product contract that is still under review. Use `core-rfc-authoring` for those cases.

## Required inputs

- Explicit approval evidence.
- Originating RFC with status `APPROVED` and its approval evidence.
- Decision identifier, scope, alternatives, consequences, and compatibility impact.

## Preconditions

- The originating RFC is explicitly `APPROVED` and its approval scope covers the decision being recorded.
- The decision is narrow enough to be recorded independently.

## Procedure

1. Read `docs/adr/README.md` and any related RFC.
2. Use `docs/engineering/templates/adr.md`.
3. Record status, date, decision drivers, considered alternatives, chosen decision, consequences, rejected options, compatibility impact, and links to evidence.
4. Keep the ADR narrow and link it from the index. Do not duplicate full implementation plans.

## Expected outputs

An ADR that makes the approval state and future constraints unambiguous.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include the ADR path, approval evidence, related RFC, status, files inspected or changed, validation, risks, and next action.

## Verification requirements

Verify that approval is evidenced, the decision is not merely proposed, the ADR is indexed, and it does not claim code or behavior that does not exist.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` if approval evidence is missing or ambiguous. Stop with `NEEDS_REVISION` if the decision scope or RFC relationship is unclear.

## References

- `docs/adr/README.md`
- `docs/engineering/templates/adr.md`
- `docs/engineering/handoff-protocol.md`
- `docs/rfc/README.md`
