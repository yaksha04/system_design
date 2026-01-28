What is Consistency?

Consistency means:

All users see the same data at the same time, no matter which server they hit.

If one user updates data, every other user should immediately see that update.

Simple definition.
Hard problem.

❌ Common Beginner Mistake

❌ “If I use a database, my system is consistent”

Wrong.

Consistency becomes a problem only in distributed systems:

Multiple servers

Replicated databases

Multiple regions

Single machine? Easy.
Distributed system? Welcome to pain.

📦 Why Consistency Is Needed

Consistency matters when:

Money is involved 💰

Correctness > availability

Wrong data = disaster

Examples:

Bank balances

Stock trading

Inventory management

Seat booking systems

If consistency breaks:

Users lose trust immediately.

⚙️ How Consistency Breaks (Reality)

Consider this setup:

1 primary database

2 replicas

Data replication takes time

Timeline:

User A updates data on primary

Replica has old data

User B reads from replica

❌ User B sees stale data

System is available, but not consistent.

📐 Types of Consistency
1️⃣ Strong Consistency

Definition:
Every read returns the most recent write.

Guarantee:

No stale data

Perfect correctness

Pros:

Easy reasoning

Critical for financial systems

Cons (Be honest):

Higher latency

Lower availability during failures

Hard to scale globally

📌 Used in: banking, transactions, payments

2️⃣ Eventual Consistency

Definition:
Data will eventually become consistent, not immediately.

Guarantee:

Temporary inconsistency allowed

System heals over time

Pros:

High availability

Better performance

Easy to scale

Cons:

Users may see stale data

Requires careful handling

📌 Used in: social media, feeds, likes, views

3️⃣ Read-Your-Writes Consistency

Guarantee:

A user always sees their own updates

Others may still see old data.

Common in:

User profile updates

Settings pages

4️⃣ Causal Consistency

Guarantee:

Related operations appear in order

Unrelated operations may not

Middle ground between strong & eventual.

⚖️ Consistency in CAP Theorem

CAP says you can choose only two:

Consistency

Availability

Partition Tolerance

When network partition happens:

Choose Consistency → system may reject requests

Choose Availability → system may serve stale data

Most modern systems:

Choose Availability + Partition Tolerance

And accept eventual consistency.

🧩 Consistency vs Availability (Truth Table)
Choice	Result
Strong Consistency	Lower availability
High Availability	Weaker consistency
Both perfectly	❌ Impossible

There is no free lunch.

🛠️ How Systems Achieve Consistency
🔹 Synchronous Replication

Write succeeds only after replicas confirm

Strong consistency

Slower

🔹 Quorum-Based Reads/Writes

Read from N nodes

Write to M nodes

Balance consistency vs availability

🔹 Leader-Based Systems

One leader handles writes

Followers replicate

Common in SQL databases.

🚧 What Causes Inconsistency

Network delays

Replication lag

Caching stale data

Async processing

Multi-region setups

Rule:

The more distributed the system, the harder consistency becomes.

🎯 Interview Thinking (Very Important)

If asked:

“What consistency does your system need?”

❌ Bad answer:

“Strong consistency because data should be correct”

✅ Good answer:

Identify data type

Choose consistency per use-case

Example:

Likes count → eventual consistency

Payment → strong consistency
