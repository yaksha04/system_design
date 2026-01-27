🧠 What is Availability?

Availability is the percentage of time a system is operational and accessible to users.

In simple words:
Can users access your system when they need it?

If your app is “perfect” but down, users don’t care.
Zero availability = zero business.

📐 How Availability Is Measured

Availability is measured as a percentage.

Availability = Uptime / (Uptime + Downtime)

Common Availability Numbers
Availability	Downtime per year
99%	~3.65 days
99.9%	~8.7 hours
99.99%	~52 minutes
99.999%	~5 minutes

📌 Each extra 9 is exponentially harder and costlier.

⚠️ Reality Check (Important)

❌ “My system is deployed on cloud, so it’s highly available”

Wrong.

Cloud gives tools, not guarantees.
Availability depends on how YOU design the system.

🧩 Why Availability Matters

Users expect 24/7 access

Downtime = revenue loss

Downtime = trust loss

Downtime = bad PR

Some systems must never go down:

Banking

Payments

Healthcare

Trading platforms

🏗️ How Systems Achieve High Availability
1️⃣ Redundancy (Most Important)

Never trust a single component.

Multiple servers

Multiple databases

Multiple availability zones

If one fails → another takes over.

2️⃣ Load Balancing

Traffic distributed across servers

Failed server removed automatically

Without load balancer:

One server dies → system dies

3️⃣ Replication

Data copied across multiple nodes

Prevents data loss during failures

Types:

Database replicas

File storage replication

4️⃣ Failover

Automatic switching when a component fails.

Examples:

Primary DB fails → replica promoted

Server crash → traffic rerouted

Failover must be:

Automatic

Fast

Reliable

5️⃣ Health Checks & Monitoring

System continuously checks:

Is server alive?

Is DB responding?

Is latency acceptable?

Unhealthy nodes are removed automatically.

🔁 Active-Active vs Active-Passive
Active-Active

All nodes handle traffic

Higher cost

Higher availability

Active-Passive

One active, one standby

Cheaper

Slower recovery

📌 Critical systems prefer Active-Active.

⚖️ Availability vs Consistency (CAP Theorem)

In distributed systems:

You cannot guarantee both during network failure.

If partition happens:

Choose Availability → may serve stale data

Choose Consistency → may reject requests

Most user-facing apps:

Prefer Availability over strict consistency

🚧 What Kills Availability (Common Mistakes)

Be honest — most outages happen because of this:

Issue	Why it hurts
Single database	Single point of failure
No monitoring	Failures unnoticed
Manual recovery	Too slow
Stateful servers	Hard to replace
Bad deployments	App goes down
🧠 Availability ≠ Reliability (Important Difference)
Availability	Reliability
Is system up?	Is system correct?
Focus on uptime	Focus on correctness
Short outages	Long-term stability

A system can be:

Highly available but buggy

Reliable but frequently down

Best systems aim for both.
