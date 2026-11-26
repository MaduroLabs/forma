# Core architecture principles

These principles guide future proposals. They are project direction, not a finalized product contract.

1. Core remains independent of UI and business domains.
2. Model selection is capability-based.
3. Providers are replaceable.
4. Hardware assumptions do not leak into generic workflow definitions.
5. Product-level skills are independently versioned and extensible.
6. Workflows are declarative.
7. Local-first execution is preferred.
8. Remote execution requires appropriate authorization.
9. Public contracts require compatibility consideration.
10. Execution failures are observable.
11. External side effects have explicit execution semantics.
12. Performance claims require evidence.
13. Abstractions are justified by real use cases.

Material decisions involving public APIs, persistence semantics, provider interfaces, security policy, or breaking changes require a Project Owner decision recorded through the RFC and ADR process.
