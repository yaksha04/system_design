What is Latency?

Latency is the time taken to process ONE request from start to finish.

📌 Measured in:

milliseconds (ms)

seconds (s)

Example

User clicks “Login”

Server responds in 200 ms

👉 Latency = 200 ms

Real-Life Analogy (Simple but Accurate)

You order coffee ☕

Time from ordering → receiving coffee = latency

Even if only one person is ordering, latency still exists.

🚀 What is Throughput?

Throughput is the number of requests processed per unit time.

📌 Measured in:

requests per second (RPS)

transactions per second (TPS)

Example

Server handles 5,000 requests per second

👉 Throughput = 5000 RPS

Real-Life Analogy

Coffee shop serves 100 customers per hour

That’s throughput

Even if each coffee takes time, throughput depends on volume, not speed of one order.

🔍 Latency vs Throughput — Side-by-Side
Feature	Latency	Throughput
Measures	Time per request	Requests per time
Unit	ms / s	RPS / TPS
Focus	Speed	Capacity
Affected by	Network, DB, code	CPU, threads, scaling
User feels	Yes	Indirectly
⚠️ Important Truth (Read This Twice)

You can have:

✅ Low Latency + ❌ Low Throughput

Very fast response

But crashes under load

Example:

A single powerful server serving 10 users very fast

❌ High Latency + ✅ High Throughput

Handles massive traffic

Individual requests are slow

Example:

Batch processing systems

✅ Low Latency + ✅ High Throughput (Ideal)

Fast responses

Scales under heavy load

This is what big tech aims for.

🧩 How Latency and Throughput Are Related

They are related but not inversely proportional.

Key relationship:

As load increases, latency usually increases

Throughput increases until a saturation point

After saturation → latency explodes, throughput drops

📌 This is called system overload

🚧 What Increases Latency?

Network delays

Database queries

Disk I/O

Lock contention

Synchronous calls

Cold starts

Rule:

Every blocking operation adds latency.

🚧 What Limits Throughput?

CPU cores

Memory

Thread pool size

Database connections

Locking & contention

I/O bandwidth

Rule:

Throughput is limited by the slowest shared resource.

⚙️ Improving Latency vs Improving Throughput
To Reduce Latency

Caching

Faster algorithms

CDN usage

Reduce network hops

Async I/O

To Increase Throughput

Horizontal scaling

Load balancing

Stateless services

Queue-based processing

Batching requests

🎯 Interview Gold (Say This, Not Buzzwords)

If interviewer asks:

“What’s more important: latency or throughput?”

Correct answer:

Depends on the system use-case.

Examples:

Trading systems → ultra-low latency

Video streaming → high throughput

Chat apps → balance of both

Batch analytics → throughput > latency

❌ Common Beginner Mistakes (Be Honest)

Confusing response time with throughput

Thinking AWS automatically fixes both

Ignoring database as bottleneck

Not measuring performance

If you don’t measure:

You’re guessing, not engineering.