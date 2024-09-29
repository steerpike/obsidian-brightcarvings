#observability

Observability is the degree to which the internal state and behaviour of a system can be inferred from its external outputs.

The pillars of observability are described as:
- Structured events
- Hypothesis-driven debugging
- Tooling that supports high cardinality, high dimensionality, and explorability

Monitoring has been conventionally expressed as using logs, metrics, and traces to approximate overall system health. The telemetry is set up ahead of time based on assumptions of how a well-understood system will operate. As such, monitoring is well-suited for well-understood and less volatile systems, such as infrastructure-level analysis.

But with shifts towards continuous delivery and cloud native practices, software grows in complexity. New software systems can have a varied and emergent state space, contingent on invariable factors. Traditional monitoring and it's assumptions might no longer be the best tool for the job.

Debugging with monitoring requires certain assumptions, and to get value from metrics requires a level of knowledge of the system and how it is supposed to function. The upper limit on effective troubleshooting is constrained by your ability to pre-declare conditions that describe what you might be looking for. The role of intuition requires extensive experience.

Monitoring is great for infrastructure, Kafka and messaging queues. These are "known territory", where you know what to look for. Observability is ideal for "unknown territory", where you might not know what to be looking for. It's hard to find what you don't know what to look for.

Structured events are key-value pairs, at an arbitrary length. The data should be high-cardinality, because this will be most useful in identifying data during debugging a system. For example, you will benefit from being able to tie data back to users, timeframes, nodes, processes, batches, etc.

Ideally the events are "wide" enough to carry all significant context variable that could influence the state space of system behavior. This can mean hundred or even thousands of key-value pairs, enabling drilling down on any combination of those keys.