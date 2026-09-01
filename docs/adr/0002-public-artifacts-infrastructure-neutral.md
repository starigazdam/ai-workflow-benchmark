# ADR-0002: Keep public benchmark artifacts infrastructure-neutral

**Date:** 2026-09-01

**Status:** Accepted

## Context

This is a public benchmark project. Contributors need clear, portable
instructions without exposing private environment details or making the
benchmark dependent on one deployment.

## Decision

Keep repository documentation, examples, scenarios, and configuration
placeholders infrastructure-neutral. Describe execution requirements in terms
of reproducible inputs and isolated execution, not private hosts, network
addresses, credentials, or deployment topology.

## Alternatives considered

- Documenting the maintainers' private environment was rejected because it
  would be unsafe and would not help external contributors reproduce results.
- Leaving environment assumptions undocumented was rejected because it would
  make scenario execution ambiguous.

## Consequences

Documentation must use generic placeholders and portable prerequisites.
Repository artifacts must not contain private infrastructure details,
credentials, or internal network information.

## Links

- Issue: #2
- [Project methodology](../../README.md)
