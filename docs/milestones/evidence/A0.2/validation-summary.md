# A0.3 validation evidence

- Reviewed baseline: `f1f9d04b53c7e64f60346a7936ef9697dcb79357`
- Final live branch HEAD: obtain from Git/GitHub at delivery; not embedded self-referentially
- Environment: Linux; Python `3.10.12`; Codex CLI `0.159.2`; no dependency installation performed. Older `0.171.0` and full-parser claims are explicitly historical.

## Checks

| Method | Result | Notes |
|---|---|---|
| Agent inventory | `PASS` | Exactly 13 `.codex/agents/*.toml` files; names match filenames and required fields are present |
| Skill inventory | `PASS` | Exactly 21 `.agents/skills/*/SKILL.md` files |
| Skill contract scan | `PASS` | All 21 front matters and required execution sections present |
| TOML structural scan | `PASS` | Dependency-free field/identifier validation over `.codex/config.toml` and 13 agent files |
| Full TOML parsing | `NOT_RUN` | Python 3.10 lacks `tomllib`; `tomli`, `toml`, `tomlq`, `yq`, Ruby TOML support, and another authorized parser were unavailable |
| Codex strict-config probe | `PASS` | `codex --cd <tree> --strict-config doctor --summary` loaded `.codex/config.toml`; this does not prove agent-TOML parsing |
| Registry mapping | `PASS` | 13/13 agents and 21/21 skills resolve in the Markdown registry |
| Markdown repository links | `PASS` | All repository-relative links resolve after adding this evidence directory |
| A0.2 decision scan | `PASS` | No new agent or standalone skill; no `core-task-execution`; runtime/storage neutrality retained |
| Product implementation scan | `PASS` | No `Cargo.toml`, `Cargo.lock`, Rust source, `src/`, provider, workflow, or M0 implementation |
| Whitespace | `PASS` | `git diff --check HEAD` exits 0 |
| Named-agent invocation | `NOT_RUN` | Current native schema exposes no named-agent selector; generic fallback disclosed |
| Cargo/product tests | `NOT_APPLICABLE` | No Rust product manifest exists |

## Parent-control preflight for delegated reviews

- Parent sandbox: `workspace-write` with restricted writable roots; the source checkout Git metadata is read-only.
- Review child write scope: explicitly none; child reports state no files changed.
- Credentials and external egress: no secrets were placed in prompts or reports; child tasks were instructed not to make external calls.
- Network/MCP: parent-only GitHub access was used for repository/PR verification and delivery; child review tasks did not use external services.
- Git publishing: only the top-level coordinator may commit, push, or create a PR; children were not authorized for those actions.
- Technical limitation: the runtime provides no per-child credential or MCP isolation. Security-sensitive work remains blocked if these controls cannot be verified for a future task.
