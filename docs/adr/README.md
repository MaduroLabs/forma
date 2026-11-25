# Architecture Decision Records

ADRs record decisions that the Project Owner has approved. A proposal is not an ADR merely because it is written down.

## Lifecycle

Architecture analysis → `PROPOSED` RFC → Project Owner review → explicit approval → `ACCEPTED` ADR → authorized implementation.

An RFC does not become approved through agent consensus, and an ADR cannot record an unapproved proposal.

## ADR status vocabulary

- `ACCEPTED`: explicitly approved and applicable.
- `SUPERSEDED`: replaced by a later accepted ADR.
- `REJECTED`: explicitly rejected by the Project Owner and retained only as a decision record.

`PROPOSED` and `UNDER_REVIEW` are RFC states, not ADR states. Draft proposals remain in `docs/rfc/`.

## Numbering and index

- Use a zero-padded numeric identifier such as `ADR-001`.
- Use the filename format `NNN-kebab-case-title.md`, for example `001-provider-neutral-capabilities.md`.
- Maintain an index table in this README with identifier, title, status, related RFC, and date.
- Link the originating RFC from every ADR for a material decision.
- A superseding ADR must link the replaced ADR; the replaced ADR becomes `SUPERSEDED`.

## Authoring rules

Use `docs/engineering/templates/adr.md`. Link the source RFC or evidence, state the approval, record consequences, and keep the decision narrow. Do not document implementation that does not exist.

No product ADRs exist yet. A0/A0.2 establish the process only. Use the ADR template's approval record, related RFC, status, consequences, and compatibility fields. Do not create an ADR for a material decision until its originating RFC is explicitly `APPROVED`.
