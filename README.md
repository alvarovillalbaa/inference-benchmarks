# inference-benchmarks

Last updated: 2026-11-10

Measure inference workloads against compatible endpoints or runtime adapters, independently of who serves the model.

**Status: planned.** This repository contains the product boundary, target
interfaces, inherited requirements, and a scoped implementation backlog. It has
no executable engine or installable package.

## Independent consumer

A user can benchmark an already running third-party or self-hosted endpoint without installing model-serving, owning the model weights, or using Lab. Local-runtime adapters are optional and explicitly configured.

## Start here

Read [the specification](docs/specs/README.md),
[implementation blueprint](docs/specs/blueprint.md), and
[scoped backlog](docs/specs/backlog.md). The specification is usable without a
runtime installation; implementation acceptance is still future work.

## Ownership

This component owns versioned workload definitions, load generation and limits,
request/response evidence, client-observed latency and throughput, optional
memory/usage/cost observations, and comparable performance reports.

[model-serving](https://github.com/alvarovillalbaa/model-serving) owns its own
endpoint lifecycle and raw request telemetry. This benchmark consumes that
endpoint like any other compatible target. Generic model quality/safety scoring
stays in open-evals or another explicit evaluation consumer.

## Composition and terms

Lab may assemble pinned releases of this component; this component never
requires Lab or a sibling checkout. Exchanges use explicit versioned artifact
or endpoint references. Optional adapters must declare their own dependencies.

[Source history and relocation map](docs/sources/README.md) explains the split.
MIT covers authored code and documentation. Third-party models, data, tools,
and services retain their own terms. No source recovery, paid job, provider
acceptance, or scientific result is established by these specifications.
