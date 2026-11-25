# Quality gates

Adapt the gates to the milestone. A gate should not require a check that the repository cannot run or that the milestone does not affect.

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

## Pull request gate

- The diff contains only intended changes.
- Required documentation is updated.
- Acceptance criteria are satisfied.
- Validation evidence is included.
- Human merge authority is preserved.

For A0, configuration parsing, skill validation, documentation links, smoke-test evidence, and absence of Core implementation are applicable. Cargo tests are not required because no Rust project exists yet.
