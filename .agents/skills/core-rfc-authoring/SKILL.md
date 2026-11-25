---
name: core-rfc-authoring
description: Draft and revise Forma Core architecture RFCs for proposed material decisions and human review.
---

Use when a proposed change affects public APIs, persistence, provider interfaces, security policy, compatibility, or another material architectural concern.

Procedure:

1. Read `docs/rfc/README.md`, relevant project policies, and existing decisions.
2. Use the template in `docs/engineering/templates/architecture-rfc.md`.
3. Define status as `PROPOSED` until the Project Owner approves it. Include context, goals, non-goals, alternatives, design, failure semantics, compatibility, security, performance, migration, and open questions.
4. Link evidence and affected files; do not state future behavior as implemented.
5. Request explicit approval and record the outcome separately from the proposal.

Expected output: a reviewable RFC with a decision request and acceptance criteria.

Verify that the RFC does not create an approved ADR prematurely, does not include product implementation, and distinguishes facts from assumptions.
