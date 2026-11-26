# Core engineering team

The repository defines 13 project-scoped custom Codex agents under `.codex/agents/`. Each standalone TOML file uses the verified required fields `name`, `description`, and `developer_instructions`.

The authoritative relationship between these agents and the 21 project skills is [the Agent–Skill Registry](skill-registry.md). The registry describes repository operating conventions and does not claim automatic native Codex selection.

| Agent | Primary ownership |
| --- | --- |
| `core-engineering-lead` | Coordination, delegation, gates, consolidation, and milestone handoffs |
| `core-architect` | Architecture, interfaces, RFCs, ADRs, and compatibility |
| `ai-research-engineer` | Primary-source AI, runtime, hardware, benchmark, and licensing research |
| `rust-systems-engineer` | Approved Rust implementation, async, errors, storage, concurrency, and tests |
| `inference-engineer` | Provider-neutral inference capabilities, discovery, routing inputs, lifecycle, streaming, and cancellation |
| `workflow-engineer` | Declarative workflows, scheduling, state, retries, cancellation, checkpointing, and recovery |
| `skill-runtime-engineer` | Future product-level skill manifests, loading, schemas, compatibility, and permissions |
| `core-code-reviewer` | Independent read-only correctness, API, regression, concurrency, and maintainability review |
| `qa-reliability-engineer` | Test strategy, conformance, fault injection, recovery, and cross-platform verification |
| `performance-engineer` | Reproducible benchmarks, profiling, resource analysis, and regressions |
| `security-engineer` | Threat modeling, trust boundaries, secrets, isolation, subprocesses, and supply chain |
| `release-engineer` | CI, packaging, dependency hygiene, reproducible builds, and release readiness |
| `developer-experience-engineer` | SDK usability, examples, contributor onboarding, and documentation quality |

Do not activate all agents for every task. The top-level session chooses the minimum set that materially improves the result.

## Operating boundaries

- The top-level session uses `core-context-management` and `core-orchestration` for substantive work.
- `core-engineering-lead` is available when the host can select the named custom agent, but it is not an additional coordinator layer.
- The parent session controls sandbox, credentials, external services, and approvals.
- Review and research roles are read-only by instruction unless an explicit documentation/report write scope is assigned.
- Every substantive assignment and completion report follows `docs/engineering/handoff-protocol.md`.
