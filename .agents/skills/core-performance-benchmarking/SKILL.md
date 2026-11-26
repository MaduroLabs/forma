---
name: core-performance-benchmarking
description: Design reproducible Forma Core benchmarks for latency, throughput, memory, CPU, scheduling, and resource regressions.
---

## When to use

Use for performance claims, benchmark design, profiling, resource allocation, or regression analysis.

## When not to use

Do not use for speculative optimization without a measured question, or to change implementation outside an assigned scope.

## Required inputs

- Performance question, workload, baseline, target, and comparison conditions.
- Hardware, OS, toolchain, dependency versions, inputs, and measurement constraints.

## Preconditions

- Baseline and candidate conditions are comparable, or the difference is explicitly reported.
- Any unavailable profiler or platform is identified before conclusions are drawn.

## Procedure

1. State the question, workload, baseline, target, and comparison conditions.
2. Record hardware, OS, toolchain, dependency versions, inputs, warmup, repetitions, timing source, and noise controls.
3. Measure before and after under equivalent conditions and preserve raw results.
4. Analyze latency distribution, throughput, CPU, memory, and confidence or uncertainty appropriate to the workload.

## Expected outputs

A benchmark report using `docs/engineering/templates/performance-benchmark.md` with reproducible commands and evidence.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md` and `docs/engineering/templates/performance-benchmark.md`. Include methodology, raw or linked evidence, results, uncertainty, unexecuted checks, risks, and next action.

## Verification requirements

Verify that no improvement is claimed without a baseline, equivalent conditions are recorded, and environment differences or unexecuted profilers are disclosed.

## Stop conditions

Stop with `BLOCKED` if the baseline or required measurement environment is unavailable. Stop with `NEEDS_REVISION` if a quantitative claim lacks reproducible evidence.

## References

- `docs/engineering/templates/performance-benchmark.md`
- `docs/engineering/quality-gates.md`
- `docs/engineering/testing-strategy.md`
