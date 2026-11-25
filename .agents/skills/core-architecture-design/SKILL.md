---
name: core-architecture-design
description: Analyze or propose Forma Core architecture, boundaries, traits, dependencies, and compatibility without finalizing unapproved contracts.
---

Use for architecture exploration, design review, interface boundaries, dependency decisions, or abstraction trade-offs.

Procedure:

1. Read `docs/project/vision.md`, `scope.md`, `non-goals.md`, and `docs/architecture/principles.md`.
2. Identify the concrete use cases, invariants, ownership boundaries, and compatibility surface.
3. Compare at least two viable alternatives when the decision is material, including trade-offs, failure modes, migration cost, and premature-abstraction risk.
4. Mark every statement as an approved decision, proposal, verified fact, assumption, open question, or limitation.
5. Put proposed contracts in an RFC and approved decisions in an ADR only after the required human approval.

Expected output: an architecture proposal or review with alternatives, risks, affected boundaries, explicit approval requests, and a verification plan.

Verify that UI, business-domain, model-family, provider, hardware, and OS concerns do not leak into generic Core abstractions and that no implementation is presented as approved design.
