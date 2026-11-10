# Inference benchmarking specification

Last updated: 2026-11-10

Status: planned. No workload runner, network transport, metric implementation,
or installable package exists yet.

## Consumer and target interface

The first consumer supplies an already running endpoint. The first adapter
targets a documented OpenAI-compatible chat protocol; it does not start or
deploy the endpoint. A local in-process runtime may be added as a separate
optional adapter.

- A benchmark request binds a versioned target/protocol with declared model
  and runtime identity; frozen workload inputs, seeds and sampling configuration;
  warm-up/measurement policy; concurrency, request, duration and byte limits;
  and output destinations.
- A workload runner records actual requests, responses, errors and timeouts,
  preserving stable sample identities and the requested concurrency schedule.
- Results report client-observed time-to-first-token and completion latency,
  latency distributions, output-token throughput and observed concurrency.
  Denominators include failed/incomplete requests explicitly.
- GPU memory and provider usage require an observable target/adapter data
  source. Cost requires a declared price/usage or billing evidence source;
  distinguish estimated, target-reported and billed values. Unknown coverage
  cannot become a measured zero.
- Comparative reports bind the exact target/workload/protocol identities,
  measurement rules, resource context and quality-evaluation references.

These are target behavioral inputs/outputs, not a released wire schema or CLI.

## Prerequisites and limits

The target must be authorized for the workload and its associated cost/data
policy. Credentials stay in external configuration. Public and local targets
must have explicit network scope. No service call or model download follows
from reading this specification.

Warm-up, caching, input/output lengths, streaming behavior, concurrency and
token accounting affect comparisons and must be declared. A caller-provided
model version does not prove an externally operated deployment is immutable.

## Acceptance

A first implementation must run in its own declared environment against a
compatible external target, preserve actual request/error evidence, enforce
limits, and produce an inspectable performance report. Deterministic transport
fixtures may validate harness behavior but are not real model benchmarks.

Quality loss from quantization or model adaptation must reference an external
quality evaluation; this repository does not duplicate Open Evals' evaluator
engine. Model-serving and Lab are optional consumers, not runtime prerequisites.

[Blueprint](blueprint.md) · [Backlog](backlog.md) ·
[Source history](../sources/README.md)
