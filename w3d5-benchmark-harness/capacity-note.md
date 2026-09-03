# Capacity note (team, one page)

## The numbers

- Locked model: Qwen/Qwen2.5-1.5B-Instruct-AWQ
- Target p95 end-to-end latency (your SLO today): 2.5 seconds
- Knee concurrency (highest concurrency whose p95 is still under target): 8
- Tokens per second at the knee: 434.2
- Max sustainable request rate at the target p95: 3.7 req/s

## The limiting family

One sentence, using this morning's triage lens (compute vs memory vs overhead):
which family limits this stack at the knee, and the tell that points to it.

- Memory-bound: throughput flattens while GPU utilisation stays moderate and p95 climbs, the decode memory-bandwidth ceiling, not compute.

## Why the knee, not the peak

One sentence in your own words on why you report the knee at the SLO rather than
the peak throughput.

- Reporting the knee guarantees the maximum throughput safely deliverable within our contractual latency SLO, whereas peak throughput reflects overloaded queues that fail acceptable response times.
