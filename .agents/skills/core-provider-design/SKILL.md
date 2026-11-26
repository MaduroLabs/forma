---
name: core-provider-design
description: Design provider-neutral inference capability contracts and replaceable adapters for heterogeneous local and remote runtimes.
---

## When to use

Use when analyzing inference providers, model descriptors, capability contracts, discovery, lifecycle, streaming, or cancellation.

## When not to use

Do not use to choose a model or route a request, to finalize a public contract without approval, or to integrate a provider unless the active milestone explicitly authorizes provider implementation.

## Required inputs

- Architecture principles and relevant RFC or assignment.
- Required capabilities, provider classes, lifecycle expectations, and failure semantics.
- Evidence for supported hardware or runtime behavior.

## Preconditions

- The design question distinguishes provider adapter behavior from model-routing policy.
- No provider-specific feature is assumed to be universal without evidence.

## Procedure

1. Read architecture principles and the relevant RFC or assignment.
2. Describe capabilities independently from model family and runtime implementation.
3. Define provider adapter boundaries, discovery inputs, observed or declared capability/resource facts, lifecycle states, streaming, cancellation, timeout, and failure semantics.
4. Consider CPU-only, NVIDIA, AMD, Apple Silicon, and remote environments without making workflow definitions hardware-aware.
5. Identify compatibility and approval needs before implementation.

## Expected outputs

A provider design or review with capability matrix, boundaries, failure semantics, alternatives, risks, and verification plan.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include capability matrix, adapter boundary, lifecycle/failure semantics, provider evidence, alternatives, risks, approval questions, and next action.

## Verification requirements

Verify that no single runtime is the public contract, hardware assumptions remain isolated, unsupported behavior is labeled, and streaming/cancellation guarantees are explicit.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` before stabilizing a public provider or capability contract. Stop with `BLOCKED` if runtime evidence is unavailable.

## References

- `docs/architecture/principles.md`
- `docs/engineering/skill-registry.md`
- `.agents/skills/core-model-routing/SKILL.md`
