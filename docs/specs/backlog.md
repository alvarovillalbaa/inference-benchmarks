# Inference benchmark backlog

Last updated: 2026-11-10

All executable capabilities remain planned.

- [ ] Freeze a small versioned workload and one external endpoint protocol binding.
- [ ] Define streaming/latency/token-count semantics, warm-up and sampling rules.
- [ ] Implement bounded dispatch with actual outputs, timeouts and error evidence.
- [ ] Aggregate latency percentiles, throughput and observed concurrency with explicit denominators.
- [ ] Add optional memory/usage/cost observation adapters with unknown coverage preserved.
- [ ] Compare independently supplied targets using matched workload/protocol identities.
- [ ] Attach external quality evaluation references for quantization/adaptation comparisons.
- [ ] Prove independent installation, transport-fixture correctness, limits and inspectable reports.
- [ ] Run an authorized real target before claiming measured model performance.

Endpoint launch, status, request execution and stop belong to
[model-serving](https://github.com/alvarovillalbaa/model-serving).
