What is CAP Theorem?

CAP Theorem states that in a distributed system, you can guarantee only TWO of the following three properties at the same time:

C — Consistency

A — Availability

P — Partition Tolerance

When a network partition happens, you must choose:
Consistency OR Availability — not both.

This is not a design choice.
This is a law of distributed systems.

❌ Biggest Beginner Misunderstanding

❌ “My system supports C, A, and P”

Wrong.

If someone says this in an interview, it’s a red flag.
CAP is about trade-offs during failure, not normal operation.

🧩 CAP Explained One by One
🟦 Consistency (C)

Definition:
All nodes return the same, latest data for a read.

If a write succeeds:

Every subsequent read sees that write

No stale data

📌 Example:

Bank balance updates

Payment confirmation

Cost:

Higher latency

Possible request rejection during failures

🟩 Availability (A)

Definition:
Every request receives a response — even during failures.

Response may not be the latest data, but:

System never says “no response”

📌 Example:

Social media feed

Likes, views, comments

Cost:

Possible stale or inconsistent data

🟥 Partition Tolerance (P)

Definition:
System continues to operate even if network communication breaks between nodes.

Reality check:

In distributed systems, network partitions WILL happen.

So:

Partition tolerance is not optional

You cannot “turn it off”

⚠️ The Real Choice in CAP

Since P is mandatory, the real decision is:

👉 During a network partition, do you choose:

CP (Consistency + Partition Tolerance)
or

AP (Availability + Partition Tolerance)

🔵 CP Systems (Consistency + Partition Tolerance)

Behavior:

System may reject requests

Ensures correct data

Used when:

Wrong data is unacceptable

Examples:

Banking systems

Payment systems

Inventory count systems

Trade-off:

Better to fail than to lie.

🟢 AP Systems (Availability + Partition Tolerance)

Behavior:

System always responds

May return stale data

Used when:

System must always stay up

Examples:

Social media

Content platforms

Messaging apps (non-critical data)

Trade-off:

Better to serve something than nothing.

❌ CA Systems (Consistency + Availability)

Not possible in real distributed systems.

Why?

Network failures are unavoidable

Without partition tolerance, system breaks

📌 CA only exists in:

Single-node systems

Non-distributed environments

🧠 CAP in Real-World Thinking

CAP is not binary.

Modern systems:

Apply different CAP choices to different parts

Payments → CP

Likes / views → AP

Notifications → AP

Account deletion → CP
