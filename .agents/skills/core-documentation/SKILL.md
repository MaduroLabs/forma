---
name: core-documentation
description: Write accurate Forma Core project, architecture, API, integration, contributor, and milestone documentation from verified evidence.
---

## When to use

Use when creating or updating repository documentation, examples, templates, or milestone reports.

## When not to use

Do not use to approve architecture, invent implementation behavior, replace the owning engineering procedure, or record transient agent transcripts.

## Required inputs

- Owning document layer.
- Source evidence and current repository state.
- Intended audience, scope, and approval status.

## Preconditions

- The document owner and source of truth are identified.
- Claims can be classified as approved decisions, proposals, facts, assumptions, or limitations.

## Procedure

1. Identify the owning document layer: `AGENTS.md`, project, architecture, RFC, ADR, engineering procedure, template, or milestone evidence.
2. Read the relevant source documents and distinguish approved decisions, proposals, facts, assumptions, and limitations.
3. Keep documentation concise, link rather than duplicate policy, and use English repository terminology.
4. Never describe proposed or missing functionality as implemented. Include commands, dates, versions, and evidence for validation claims.
5. Review cross-document links and contradictions before handoff.

## Expected outputs

The changed document list, source evidence, assumptions, unresolved questions, and validation performed.

## Handoff requirements

Use `docs/engineering/handoff-protocol.md`. Include changed paths, source evidence, claims requiring approval, links checked, assumptions, unresolved questions, and next action.

## Verification requirements

Verify links resolve, templates contain actionable fields, no transcript or secret was committed, live external state is not presented as verified without evidence, and the document owner is appropriate.

## Stop conditions

Stop with `NEEDS_HUMAN_APPROVAL` if documentation would record an unapproved decision. Stop with `BLOCKED` if authoritative source evidence is unavailable.

## References

- `AGENTS.md`
- `docs/engineering/handoff-protocol.md`
- `docs/project/current-state.md`
