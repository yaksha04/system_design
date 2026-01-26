System Design — Complete Beginner Notes
🧠 What is System Design?

System Design is the process of designing the architecture of a software system so that it can:

Handle large numbers of users

Scale when traffic grows

Stay reliable even when parts fail

Be maintainable and cost-effective

In simple words:

System Design answers: “How will this app work when millions of users start using it?”

❌ What System Design is NOT

Let’s clear common confusion (this trips many beginners):

❌ Not System Design	                     ✅ Actually System Design
Writing code	                              Designing how components interact
Choosing a programming language	              Choosing databases, caches, queues
UI/UX design	                              Backend + infrastructure design
DSA problems	                              Architecture & scalability

If you think System Design = drawing boxes randomly → that’s wrong.

🏗️ High-Level View of a System

A real-world system usually has:

Client (Web / Mobile App)

Backend Servers

Database

Cache

Load Balancer

Message Queue

External Services

🧩 Core Components of System Design
1️⃣ Client

Browser or mobile app

Sends requests (HTTP/HTTPS)

Receives responses (JSON / HTML)

Example: Chrome, Android App, iOS App

2️⃣ Backend / Application Server

Contains business logic

Handles authentication, validation, processing

Examples:

Node.js (Express)

Java (Spring Boot)

Python (Django / FastAPI)

3️⃣ Database

Stores persistent data.

Types:

Relational (SQL) → MySQL, PostgreSQL

NoSQL → MongoDB, Cassandra, DynamoDB

💡 Rule of thumb:

Structured data → SQL

Massive scale / flexible schema → NoSQL

4️⃣ Cache

Used to reduce database load and improve speed.

Examples:

Redis

Memcached

📌 Cache stores frequently accessed data in memory.

5️⃣ Load Balancer

Distributes traffic across multiple servers.

Why?

Prevents server overload

Improves availability

Examples:

NGINX

HAProxy

AWS ALB

6️⃣ Message Queue

Used for asynchronous processing.

Examples:

RabbitMQ

Apache Kafka

AWS SQS

Use cases:

Email sending

Notifications

Background jobs

7️⃣ Storage

Stores files like:

Images

Videos

PDFs

Examples:

AWS S3

Google Cloud Storage

⚖️ Key System Design Concepts (VERY IMPORTANT)
🔹 Scalability

Ability to handle more users.

Types:

Vertical Scaling → Bigger server (CPU/RAM)

Horizontal Scaling → More servers (preferred)

🔹 Reliability

System should not crash on failures.

Achieved using:

Replication

Failover

Health checks

🔹 Availability

System should be up and running.

Measured using uptime:

99.9% = ~8.7 hours downtime/year

99.99% = ~52 minutes/year

🔹 Latency

Time taken to respond to a request.

Lower latency = better user experience.

🔹 Consistency vs Availability (CAP Theorem)

In distributed systems, you can’t have all three:

Consistency

Availability

Partition Tolerance

You must compromise one.

🏛️ Monolith vs Microservices
Monolithic Architecture

Single codebase

Easy to build initially

Hard to scale later

Microservices Architecture

Small independent services

Scales well

More complex infrastructure

Most startups:

Start monolith → Move to microservices later

🌍 Real-World System Design Examples

You should be able to design (at least at high level):

URL Shortener (like Bitly)

Chat Application (like WhatsApp)

Video Streaming (like Netflix)

Ride Booking (like Uber)