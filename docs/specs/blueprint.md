# Inference benchmark implementation blueprint

Last updated: 2026-11-10

Status: planned. Derived from the measurement portion of original Lab section
17. The [relocation map](../sources/repository-expansion-map.json) identifies
the mixed source and its preserved snapshot.

## Measurement first

Start with one explicit external endpoint binding and a frozen small workload.
Define client timestamps, streaming/first-token semantics, warm-up, token
accounting and limits before adding concurrency sweeps. Capture actual outputs,
errors, incomplete requests and the target's declared identity.

## Original measurement requirements

The original design requests p50/p95 time-to-first-token, output tokens/sec,
maximum observed concurrency, GPU memory, input/output token cost and
quantization-quality comparisons. This owner maintains the workload,
aggregation and reporting methodology. Model-serving can emit observations
but does not own benchmark definitions.

Memory and cost need an explicit observation source. A remote endpoint that
does not expose them yields unknown/unsupported cells. Quality comparisons
link external evaluation results under matched inputs; performance results do
not silently stand in for quality or safety evidence.

## Independent comparisons

Compare externally supplied base, post-trained, distilled or quantized targets
under declared matched workloads. Do not require a target to come from your
own trainers or serving toolkit. Preserve runtime/resource differences instead
of treating unlike deployments as controlled experiments.
