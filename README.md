# ai-workflow-benchmark

A harness for benchmarking AI coding agents against fixed, reproducible tasks.

Compare **models**, **workflow configs**, **skills/instructions**, and **runner backends** on your own repos — measuring test pass rate, token consumption, cost, tool-call patterns, and code quality.

## What it does

Given a **scenario** (repo + base commit + PRD + DoD unit tests) and one or more **variants** (model + runner + workflow + skills), the benchmark:

1. Checks out the repo at the base commit in an isolated Docker container (no agent memory, no cross-run bleed)
2. Injects skills/instructions as context and runs the workflow via [ai-workflow-runner](https://github.com/starigazdam/ai-workflow-runner)
3. Evaluates the output: runs DoD unit tests, lint, LoC delta, test-to-code ratio
4. Collects metrics from runner artifacts: input/output tokens, cost USD, tool calls, errors, wall time
5. Aggregates across N repeated runs and emits a comparison table

## Status

🚧 Under construction — see [issue #1](../../issues/1) for the implementation plan.

## Concepts

- **Scenario** — `scenarios/*.yaml`: repo + base_commit + PRD + dod_tests + quality_gates
- **Variant** — `variants/*.yaml`: model + runner + workflow.yaml + skills + instructions
- **Run** — one (scenario × variant) execution; each run is isolated
- **Report** — aggregated Markdown table + JSONL across all runs for a scenario

## Architecture decisions

Significant, durable decisions about benchmark methodology and project
boundaries are recorded in [Architecture Decision Records](docs/adr/README.md).

## Related

- [ai-workflow-runner](https://github.com/starigazdam/ai-workflow-runner) — the workflow execution engine this wraps
