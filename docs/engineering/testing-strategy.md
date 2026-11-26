# Testing strategy

The repository currently contains no Rust manifest or product implementation. A0 therefore validates engineering infrastructure and does not require Cargo tests.

Future milestones should select the smallest effective mix of:

- Unit tests for local invariants and error paths.
- Integration tests for module and storage boundaries.
- Provider conformance tests for capability contracts.
- Contract tests for public schemas and compatibility.
- Reliability and fault-injection tests for retries, cancellation, checkpoints, crash recovery, and side effects.
- Cross-platform tests for supported operating systems and hardware classes where applicable.
- Performance benchmarks with reproducible baselines and conditions.

Every report records the command, environment, result, skipped checks, and reason. A test that was not run is not a passing test.
