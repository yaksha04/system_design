What is a Load Balancer?

A Load Balancer (LB) is a system that distributes incoming traffic across multiple servers to ensure:

No single server is overloaded
High availability
Better performance

In simple words:
It acts like a traffic police for requests.

❌ Reality Check

❌ “If I have multiple servers, I don’t need a load balancer”

Wrong.

Without a load balancer:

Some servers get overloaded
Some remain idle
Failures are not handled properly
🏗️ Basic Working

Flow:

Client sends request
Request hits load balancer
LB chooses a backend server
Server responds
LB returns response to client
🎯 Why Load Balancer is Important
Prevents server overload
Enables horizontal scaling
Improves fault tolerance
Ensures high availability

Without LB:

Your scalability plan is incomplete.

🧩 Types of Load Balancer (Core Classification)
1️⃣ Layer 4 Load Balancer (Transport Layer)

Works at:

TCP / UDP level
How it works:
Routes based on:
IP address
Port number

📌 It does NOT look inside the request.

✅ Advantages
Very fast
Low latency
High throughput
❌ Disadvantages
No content-based routing
Limited flexibility
📌 Use Cases
High-performance systems
Simple routing needs
2️⃣ Layer 7 Load Balancer (Application Layer)

Works at:

HTTP / HTTPS level
How it works:
Routes based on:
URL path (/api, /login)
Headers
Cookies

📌 It understands the request content.

✅ Advantages
Smart routing
Supports microservices
Can handle authentication, caching
❌ Disadvantages
Slower than L4
More complex
📌 Use Cases
Web applications
APIs
Microservices architectures
⚖️ L4 vs L7 Comparison
Feature	Layer 4	Layer 7
Level	Transport	Application
Speed	Faster	Slightly slower
Routing	IP + Port	Content-based
Flexibility	Low	High
Use case	Simple systems	Complex apps
🔁 Load Balancing Algorithms

Load balancer doesn’t randomly choose servers (well… sometimes it does 😄)

1️⃣ Round Robin
Requests distributed sequentially

Example:

Req1 → Server1
Req2 → Server2
Req3 → Server3

✔ Simple
❌ Ignores server load

2️⃣ Least Connections
Sends request to server with fewest active connections

✔ Better load distribution
❌ Slightly complex

3️⃣ IP Hash
Same client → same server

✔ Useful for session persistence
❌ Can cause uneven load

4️⃣ Weighted Round Robin
Servers assigned weights based on capacity

✔ Better for mixed hardware
❌ Needs tuning

🔒 Sticky Sessions (Session Persistence)
Same user always goes to same server
Why needed?
When server stores session data
Problem:
Breaks scalability
Bad for fault tolerance

📌 Better approach:

Use stateless servers + shared session store (Redis)

🧠 Types Based on Deployment
1️⃣ Hardware Load Balancer
Physical device
Expensive
High performance
2️⃣ Software Load Balancer

Examples:

NGINX
HAProxy

✔ Flexible
✔ Cheap
✔ Widely used

3️⃣ Cloud Load Balancer

Examples:

AWS ALB / NLB
Google Cloud LB

✔ Managed
✔ Auto-scaling
✔ Easy integration

🚧 Common Mistakes
Mistake	Why it’s bad
No health checks	Sends traffic to dead servers
Sticky sessions everywhere	Poor scalability
Single load balancer	Single point of failure
Wrong algorithm	Uneven load
🧠 High Availability for Load Balancer

Even load balancer can fail 😬

Solution:

Multiple load balancers
DNS-based routing
Failover mechanisms
🎯 Interview-Ready Answer

If asked:

“What is a load balancer?”

Answer:

A load balancer distributes incoming traffic across multiple servers to ensure high availability, fault tolerance, and efficient resource utilization.
