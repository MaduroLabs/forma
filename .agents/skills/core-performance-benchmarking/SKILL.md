---
name: core-performance-benchmarking
description: Design reproducible Forma Core benchmarks for latency, throughput, memory, CPU, scheduling, and resource regressions.
---

Use for performance claims, benchmark design, profiling, resource allocation, or regression analysis.

Procedure:

1. State the question, workload, baseline, target, and comparison conditions.
2. Record hardware, OS, toolchain, dependency versions, inputs, warmup, repetitions, timing source, and noise controls.
3. Measure before and after under equivalent conditions and preserve raw results.
4. Analyze latency distribution, throughput, CPU, memory, and confidence or uncertainty appropriate to the workload.

Expected output: a benchmark report using `docs/engineering/templates/performance-benchmark.md` with reproducible commands and evidence.

Verify that no improvement is claimed without a baseline and that environment differences or unexecuted profilers are disclosed.
