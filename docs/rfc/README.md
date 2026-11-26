# Architecture RFCs

RFCs are reviewable proposals for material architecture or policy decisions. They do not authorize implementation and do not become approved decisions without explicit Project Owner approval.

The lifecycle is: `PROPOSED` → `UNDER_REVIEW` → `APPROVED`, `REJECTED`, `WITHDRAWN`, or `SUPERSEDED`. Only an explicitly `APPROVED` RFC with approval evidence may lead to an accepted ADR. An RFC never authorizes implementation by itself.

## RFC status vocabulary

- `PROPOSED`: drafted and not yet under formal review.
- `UNDER_REVIEW`: actively awaiting Project Owner review.
- `APPROVED`: explicitly approved with scope and conditions recorded.
- `REJECTED`: explicitly not approved.
- `WITHDRAWN`: removed by its owner before a decision.
- `SUPERSEDED`: replaced by a later RFC or decision.

Use `docs/engineering/templates/architecture-rfc.md`. Include context, goals, non-goals, alternatives, design, failure and compatibility semantics, security and performance considerations, migration, open questions, and an explicit approval request.

No product RFCs exist yet. A0/A0.2 establish the proposal process only. Record approval scope, conditions, date when available, and a concise reference to the Project Owner's explicit approval; never invent approval evidence or commit private conversation transcripts.
