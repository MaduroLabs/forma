---
name: core-adr-authoring
description: Record approved Forma Core architecture decisions with context, consequences, and traceable evidence.
---

Use only after the Project Owner has approved a material decision or explicitly requested an ADR recording an already-approved choice.

Procedure:

1. Read `docs/adr/README.md` and any related RFC.
2. Use `docs/engineering/templates/adr.md`.
3. Record status, date, decision drivers, considered alternatives, chosen decision, consequences, rejected options, compatibility impact, and links to evidence.
4. Keep the ADR narrow and link it from the index. Do not duplicate full implementation plans.

Expected output: an ADR that makes the approval state and future constraints unambiguous.

Verify that approval is evidenced, the decision is not merely proposed, and the ADR does not claim code or behavior that does not exist.
