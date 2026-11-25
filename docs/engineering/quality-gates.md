# Quality gates

Adapt the gates to the milestone. A gate should not require a check that the repository cannot run or that the milestone does not affect.

Use results `PASS`, `FAIL`, `NOT_APPLICABLE`, `NOT_RUN`, or `BLOCKED`. `NOT_RUN` is never a pass and requires a reason.

## Architecture gate

- Scope and non-goals are clear.
- Relevant principles and accepted ADRs are respected.
- Breaking changes are identified.
- Required human approvals are recorded.

## Implementation gate

- Implementation matches approved requirements.
- Changes remain within scope.
- No unnecessary abstraction was introduced.
- Errors and failure paths are handled explicitly.

## Verification gate

- Applicable tests pass.
- Regression tests exist when needed.
- Cross-platform limitations are documented.
- Unexecuted tests are disclosed with reasons.

## Review gate

- Independent review is complete when required.
- Blocking findings are resolved.
- Unresolved findings are disclosed.
- Security-sensitive changes receive appropriate review.

## Trigger matrix

| Gate | Mandatory when the change affects |
| --- | --- |
| Architecture | Public contracts, dependency boundaries, compatibility, provider abstraction, persistence guarantees, or material architecture |
| Contract | Public APIs, capability/provider contracts, workflow schemas, product skill manifests, or storage interfaces |
| Reliability | Scheduling, execution state, retry, cancellation, checkpoints, crash recovery, persistence, side effects, or long-running operations |
| Security | Secrets, filesystem/network, subprocesses, untrusted skills/content, tools, cloud execution, data transmission, trust boundaries, or security-sensitive dependencies |
| Performance | Inference/routing/scheduler hot paths, resource allocation, memory lifecycle, performance-sensitive storage, or quantitative claims |
| Cross-platform | OS APIs, native dependencies, filesystem/process behavior, hardware detection, accelerators, or platform build configuration |
| Release | CI, manifests, lockfiles, package contents, versions, artifacts, reproducible builds, dependency licensing, or supply chain |

Quantitative performance claims require a measured baseline and comparable conditions. Cross-platform gates report actual coverage; unsupported platforms are not silently treated as passing.

## Evidence contract

Each applicable check records the command or method, environment, expected result, actual result, status, evidence reference, limitations, and reason when skipped. Static inspection, parsing, local execution, generic native delegation, named-agent invocation, and cross-platform CI are distinct evidence classes.

## Pull request gate

- The diff contains only intended changes.
- Required documentation is updated.
- Acceptance criteria are satisfied.
- Validation evidence is included.
- Human merge authority is preserved.

For A0, configuration parsing, skill validation, documentation links, smoke-test evidence, and absence of Core implementation are applicable. Cargo tests are not required because no Rust project exists yet.
