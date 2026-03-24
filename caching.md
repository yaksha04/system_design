Caching & Cache Eviction — System Design Notes
🧠 What is Caching?

Caching is the technique of storing frequently accessed data in a faster storage layer (usually memory) so that future requests can be served quickly.

In simple words:
Don’t recompute or fetch again — reuse it.

❌ Reality Check

❌ “Caching makes everything fast”

Half-truth.

Caching:

Improves speed ✅
Adds complexity ❌
Can return stale data ❌

Bad caching can break your system silently.

🏗️ Basic Flow of Caching

Flow:

Client sends request
System checks cache
✅ Cache Hit → return data
❌ Cache Miss → fetch from DB → store in cache → return
🎯 Why Caching is Important
Reduces database load
Improves response time (low latency)
Increases throughput
Saves compute cost

Rule:

If your DB is slow → add caching before blaming database

🧩 Types of Caching
1️⃣ Client-Side Cache
Stored in browser / app
Example: browser cache, mobile app cache
2️⃣ CDN Cache
Content cached geographically closer to users

Examples:

Images, videos, static files
3️⃣ Application Cache
Cache inside application layer

Examples:

In-memory cache
Redis, Memcached
4️⃣ Database Cache
DB internally caches query results
⚙️ Caching Strategies (VERY IMPORTANT)
1️⃣ Cache-Aside (Lazy Loading)

Flow:

App checks cache
If miss → fetch from DB → update cache

✔ Most commonly used
❌ First request is slow

2️⃣ Write-Through

Flow:

Write goes to cache AND DB together

✔ Data always consistent
❌ Slower writes

3️⃣ Write-Back (Write-Behind)

Flow:

Write goes to cache first
DB updated later asynchronously

✔ Fast writes
❌ Risk of data loss

4️⃣ Read-Through
Cache itself fetches data from DB

✔ Cleaner abstraction
❌ Less control

⚠️ Cache Invalidation (Hardest Problem)

“There are only two hard things in CS:
cache invalidation and naming things.”

Why hard?

Data changes
Cache becomes stale
Users see outdated info
🗑️ Cache Eviction (Core Topic)

Cache has limited memory, so old data must be removed.

Cache Eviction = deciding what to remove when cache is full

🔁 Cache Eviction Policies
1️⃣ LRU (Least Recently Used)
Removes data that was not used recently

✔ Most widely used
✔ Works well for real-world traffic

📌 Assumption:

Recently used data will be used again

2️⃣ LFU (Least Frequently Used)
Removes data used least number of times

✔ Good for stable access patterns
❌ Fails if usage pattern changes suddenly

3️⃣ FIFO (First In First Out)
Removes oldest data

✔ Simple
❌ Not intelligent

4️⃣ TTL (Time-To-Live)
Data expires after fixed time

✔ Prevents stale data
❌ May remove useful data

5️⃣ Random Eviction
Removes random entries

✔ Simple
❌ Unpredictable

⚖️ Choosing the Right Eviction Policy
Policy	Best Use Case
LRU	General applications
LFU	Predictable usage
TTL	Time-sensitive data
FIFO	Simple systems

📌 In real-world:

LRU + TTL combination is very common
