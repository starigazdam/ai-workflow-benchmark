# ADR-0001: Reproducible isolated agent evaluations

**Date:** 2026-09-01

**Status:** Accepted

## Context

The project compares AI coding agents, workflow configurations, skills, and
runner backends. Results are only useful when variants run against the same
scenario and quality gates without memory or filesystem state leaking between
runs.

## Decision

Model benchmark work as fixed scenarios and variants. Run each scenario ×
variant execution in an isolated container at a pinned repository base commit,
then evaluate it with the scenario's defined tests and quality gates. Aggregate
repeated runs into comparable reports.

## Alternatives considered

- Running agents directly in a shared development checkout was rejected because
  prior runs and local state could influence later results.
- Comparing agents with informal prompts and no fixed acceptance checks was
  rejected because it would not produce reproducible measurements.

## Consequences

Scenarios must identify a base commit and explicit quality gates. Isolation and
repetition add execution cost, but make pass rates, token usage, cost, tool
calls, and code-quality measurements comparable across variants.

## Links

- Issue: #1
- [Project methodology](../../README.md)
