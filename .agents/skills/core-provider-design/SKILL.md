---
name: core-provider-design
description: Design provider-neutral inference capability contracts and replaceable adapters for heterogeneous local and remote runtimes.
---

Use when analyzing inference providers, model descriptors, capability contracts, discovery, lifecycle, streaming, or cancellation.

Procedure:

1. Read architecture principles and the relevant RFC or assignment.
2. Describe capabilities independently from model family and runtime implementation.
3. Define provider adapter boundaries, discovery inputs, resource estimates, lifecycle states, streaming, cancellation, timeout, and failure semantics.
4. Consider CPU-only, NVIDIA, AMD, Apple Silicon, and remote environments without making workflow definitions hardware-aware.
5. Identify compatibility and approval needs before implementation.

Expected output: a provider design or review with capability matrix, boundaries, failure semantics, alternatives, risks, and verification plan.

Verify that no single runtime is treated as the public contract, hardware assumptions remain isolated, and unverified support is labeled.
