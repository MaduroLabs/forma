# Forma Core vision

Status: project direction supplied by the Project Owner. Detailed product contracts remain proposals until approved.

Forma Core is a modular, model-agnostic, local-first AI workflow engine written in Rust. It is intended to be a reusable library and execution foundation that a separate application repository can consume.

The eventual Core should support capability-based model abstraction, replaceable local and remote inference providers, hardware-aware discovery and routing, extensible product-level skills, declarative workflows, scheduling and execution, persistent state, cancellation, retry, checkpointing, crash recovery, human approval gates, resource management, secure tool execution, and public SDK interfaces.

Core stays independent of desktop UI frameworks, marketing logic, specific AI model families, specific inference providers, specific operating systems, and company workflows.

The engineering team must optimize for clear boundaries, local-first behavior, observable failures, compatibility-aware public contracts, and evidence-backed quality.
