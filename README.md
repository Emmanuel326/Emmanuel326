# About Me

I break things on purpose to understand how they actually work.

Most developers want frameworks to hide complexity. I want to see the cache line thrashing, the spurious wakeups, the exact moment the page cache betrays you. I write code that makes the kernel show its cards.

**What I do:** Systems programming where nanoseconds matter and assumptions get you killed. I build concurrency primitives from scratch, measure syscall latency until the variance disappears, and containerize processes without Docker because I need to know what PID 1 is *actually* doing when signals arrive.

**What drives me:** The gap between what people think is happening and what's happening at the CPU and kernel level. False sharing that benchmarks miss. Backpressure semantics that look correct until they're under contention. The lies that abstractions tell when you don't verify.

I don't trust the happy path. I trust experiments, measurements, and code that fails predictably.

---

## The Work

My repositories aren't demos — they're forensic investigations:

- **false-sharing**: A 2×2 matrix that proves when cache coherence becomes your bottleneck
- **mutex_condvar**: Bounded queues built to survive high contention and graceful shutdown
- **syslat**: Measuring what `pread()` actually costs when page cache warmth varies
- **procjail**: PID namespaces, signal forwarding, and orphan reaping without container magic

Each one forces a confrontation with kernel behavior, memory subsystems, or scheduling reality.

---
## How I Verify Reality

I don't trust results until they survive:
- CPU pinning and isolated cores
- warm vs cold cache runs
- variance analysis, not single numbers
- instrumentation (`perf`, tracing, explicit counters)

If an effect disappears when conditions change, it wasn’t a property — it was noise.


## The Philosophy

Frameworks smooth over sharp edges. I sharpen them.

Abstractions hide failure modes. I expose them.

Benchmarks lie. Experiments with controlled variables don't.

If your mental model survives contact with real hardware, real contention, and real failure — it might be correct. Until then, it's just wishful thinking wrapped in clean APIs.

---

**Current focus:** Making concurrency primitives that don't just work in theory, observability that measures truth instead of approximations, and performance engineering where "fast enough" isn't a technical term.

The code is minimal. The understanding is maximal.

---

*Find me on [GitHub](https://github.com/Emmanuel326) — where every commit is a question the kernel has to answer.*

If you're new here, start with **false-sharing** — it's the smallest repo and the fastest way to recalibrate your mental model of "shared memory."

