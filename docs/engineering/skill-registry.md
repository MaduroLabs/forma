# Agent–Skill Registry

This Markdown registry is the authoritative repository-level mapping between the 13 Forma Core custom agents and the 21 engineering skills. It is an engineering convention, not proof of automatic Codex skill activation or named-agent selection.

The top-level session selects the minimum relevant skills and agents. Primary ownership does not prevent necessary collaboration.

## Primary ownership

| Agent | Primary skills | Typical supporting skills |
| --- | --- | --- |
| `core-engineering-lead` | `core-orchestration`, `core-context-management`, `core-milestone-management`, `core-git-workflow` | `core-documentation`, all relevant domain skills |
| `core-architect` | `core-architecture-design`, `core-rfc-authoring`, `core-adr-authoring` | `core-provider-design`, `core-model-routing`, `core-workflow-design`, `core-persistence-design`, `core-skill-runtime-design`, `core-technical-research` |
| `ai-research-engineer` | `core-technical-research` | `core-provider-design`, `core-model-routing`, `core-performance-benchmarking`, `core-security-review` |
| `rust-systems-engineer` | `core-rust-development`, `core-persistence-design` | `core-contract-testing`, `core-reliability-testing`, `core-security-review`, `core-workflow-design` |
| `inference-engineer` | `core-provider-design`, `core-model-routing` | `core-architecture-design`, `core-technical-research`, `core-performance-benchmarking`, `core-contract-testing`, `core-security-review` |
| `workflow-engineer` | `core-workflow-design` | `core-persistence-design`, `core-reliability-testing`, `core-contract-testing`, `core-rust-development` |
| `skill-runtime-engineer` | `core-skill-runtime-design` | `core-architecture-design`, `core-security-review`, `core-contract-testing`, `core-rfc-authoring` |
| `core-code-reviewer` | `core-code-review` | `core-architecture-design`, `core-contract-testing`, `core-reliability-testing`, `core-security-review`, `core-performance-benchmarking` |
| `qa-reliability-engineer` | `core-contract-testing`, `core-reliability-testing` | `core-workflow-design`, `core-provider-design`, `core-skill-runtime-design`, `core-code-review` |
| `performance-engineer` | `core-performance-benchmarking` | `core-model-routing`, `core-provider-design`, `core-technical-research`, `core-release-management` |
| `security-engineer` | `core-security-review` | `core-architecture-design`, `core-skill-runtime-design`, `core-provider-design`, `core-release-management`, `core-code-review` |
| `release-engineer` | `core-release-management` | `core-git-workflow`, `core-security-review`, `core-performance-benchmarking`, `core-documentation` |
| `developer-experience-engineer` | `core-documentation` | `core-rfc-authoring`, `core-adr-authoring`, `core-git-workflow`, `core-release-management` |

## Activation and exclusions

| Skill family | Activate when | Do not activate for |
| --- | --- | --- |
| Governance | Session recovery, milestone state, substantive coordination, branch/PR delivery | Unrelated product implementation details without the relevant procedure |
| Architecture and research | A material boundary, decision, alternative, or external evidence question exists | Routine implementation with an approved specification |
| Core engineering | Approved Rust, provider, routing, workflow, product-skill, or persistence work is in scope | Unapproved product contracts or infrastructure-only tasks that do not touch the product |
| Quality assurance | A change requires independent correctness, contract, reliability, performance, or security evidence | Review of a non-existent implementation or unsupported quantitative claim |
| Distribution and maintenance | Documentation, CI, packaging, dependency, release, or Git delivery is in scope | Merging, publishing, or changing protection settings |

## Responsibility boundaries

- `core-context-management` recovers state; it does not plan tasks or publish Git changes.
- `core-milestone-management` owns milestone states and evidence; it does not delegate or implement.
- `core-orchestration` coordinates; it does not replace specialist procedures.
- `core-git-workflow` owns branch, commit, push, and PR delivery; it does not merge.
- `core-architecture-design` owns cross-domain boundaries; domain skills own their specialist semantics.
- `core-provider-design` owns provider/capability contracts and provider-reported capability/resource facts; `core-model-routing` owns estimation policy, suitability interpretation, selection, and execution policy.
- `core-workflow-design` owns when a checkpoint or external-side-effect transition is required; `core-persistence-design` owns how checkpoint, idempotency, and reconciliation records are represented and committed.
- `core-rust-development` implements approved changes; `core-code-review` remains independently read-only.
- `core-contract-testing` verifies contracts; `core-reliability-testing` verifies failure and recovery behavior.
- `core-release-management` owns CI/package/reproducibility readiness; `core-git-workflow` owns branch/PR delivery.
- `core-skill-runtime-design` concerns future product skills, not `.agents/skills/` engineering skills.

## Typical handoffs and review triggers

- Architecture analysis → RFC authoring → Project Owner approval → ADR authoring.
- Provider design → model routing and contract testing.
- Workflow design → persistence design and reliability testing.
- Rust implementation → code review plus applicable contract, reliability, security, performance, and release gates.
- Documentation or milestone work → documentation validation and coordinator consolidation.

Security review is mandatory for secrets, filesystem, network, subprocess, untrusted content, tools, remote execution, or security-sensitive dependencies. Performance review is mandatory for hot paths, routing, scheduling, resource, memory, or explicit performance claims. Release review is mandatory for CI, manifests, locks, package contents, versions, artifacts, or reproducibility changes.

## Permissions and runtime status

Review and research roles are intended to be read-only by instruction. Actual sandbox, credential, and GitHub enforcement remains parent-controlled. A generic native subagent with an assigned role is not evidence that a named TOML custom agent was selected. Record the invocation mode in every substantive handoff.

## Authoritative references

- `AGENTS.md`
- `docs/engineering/handoff-protocol.md`
- `docs/engineering/quality-gates.md`
- `docs/engineering/milestone-lifecycle.md`
- `docs/engineering/agent-permissions.md`
