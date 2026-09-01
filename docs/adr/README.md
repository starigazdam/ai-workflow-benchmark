# Architecture Decision Records

This directory records significant, durable architectural decisions for
`ai-workflow-benchmark`. ADRs explain *why* a choice was made, including its
trade-offs, so contributors do not need to reconstruct the rationale from
issues or pull requests.

## When to write an ADR

Create or update an ADR when a decision has a durable, cross-cutting impact on
benchmark methodology, evaluation criteria, isolation, data handling, runner
integration, or another core project boundary. Routine implementation details
belong in issues, pull requests, and code documentation instead.

## Lifecycle

- **Proposed** — under discussion and not yet governing the project.
- **Accepted** — the current decision.
- **Superseded** — replaced by a newer ADR; link to its replacement.
- **Deprecated** — no longer applicable without a direct replacement.

Accepted ADRs are not rewritten to reverse a decision. Record a changed
choice in a new ADR and link the records together.

## Naming and numbering

Use zero-padded, monotonic identifiers and a short lowercase slug:
`0001-reproducible-isolated-agent-evaluations.md`. Do not reuse an identifier.

## Template

- [ADR template (not a decision record)](0000-template.md)

## Decision records

- [ADR-0001: Reproducible isolated agent evaluations](0001-reproducible-isolated-agent-evaluations.md)
- [ADR-0002: Keep public benchmark artifacts infrastructure-neutral](0002-public-artifacts-infrastructure-neutral.md)
