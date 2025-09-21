# ![System Design](https://img.shields.io/badge/System-Design-blue?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Questions-green?style=for-the-badge) ![Production Ready](https://img.shields.io/badge/Production-Ready-orange?style=for-the-badge)

# System Design Interview Questions & Answers


---

<details>
<summary><strong>1. Basics</strong></summary>

- ⚡ **What is System Design?**  
  Designing the architecture of large-scale applications considering scalability, reliability, and maintainability.

- **Difference between Monolithic and Microservices architecture?**  
  Monolithic: Single deployable unit; Microservices: Multiple independent services.

- **What are the main components of a system?**  
  Client, Server, Database, Cache, Load Balancer, Queue.

- **What is horizontal vs vertical scaling?**  
  Horizontal: Add more machines; Vertical: Upgrade existing machine.

</details>

<details>
<summary><strong>2. Scalability</strong></summary>

- **How do you scale an application?**  
  Scale vertically or horizontally, use caching, database sharding, and load balancers.

- **What is the difference between strong and eventual consistency?**  
  Strong: All nodes see the same data immediately; Eventual: Nodes eventually converge.

- **⚡ How to handle high traffic spikes?**  
  Auto-scaling, load balancing, queue-based asynchronous processing.

</details>

<details>
<summary><strong>3. Load Balancing</strong></summary>

- **What is a Load Balancer?**  
  Distributes incoming requests across multiple servers to improve availability.

- **Types of Load Balancers?**  
  Layer 4 (TCP), Layer 7 (HTTP), DNS-based, Hardware vs Software.

- **⚡ How does sticky session work?**  
  Routes user requests to the same server using cookies or session IDs.

</details>

<details>
<summary><strong>4. Caching</strong></summary>

- **Why use caching?**  
  Reduce latency and offload database queries.

- **Types of cache?**  
  In-memory (Redis, Memcached), CDN, Browser cache.

- **⚡ Cache invalidation strategies?**  
  Time-to-Live (TTL), Write-through, Write-behind, Manual purge.

</details>

<details>
<summary><strong>5. Database Design</strong></summary>

- **SQL vs NoSQL?**  
  SQL: Structured, ACID; NoSQL: Flexible schema, horizontal scaling.

- **⚡ When to use a relational database?**  
  For transactions, complex queries, and strict consistency.

- **⚡ When to use a NoSQL database?**  
  For high write throughput, flexible schema, and horizontal scaling.

</details>

<details>
<summary><strong>6. Indexing & Query Optimization</strong></summary>

- **What is an index?**  
  Data structure to improve query speed.

- **Types of indexes?**  
  B-Tree, Hash, Composite, Full-text.

- **⚡ How to optimize slow queries?**  
  Indexing, query rewriting, denormalization, caching frequent queries.

</details>

<details>
<summary><strong>7. Microservices & SOA</strong></summary>

- **What is Microservices architecture?**  
  Small, independent services communicating via APIs.

- **⚡ Difference between SOA and Microservices?**  
  SOA: Shared enterprise service bus; Microservices: Lightweight, decentralized.

- **How to handle inter-service communication?**  
  Synchronous (REST/gRPC) or Asynchronous (Message Queues).

</details>

<details>
<summary><strong>8. Message Queues & Asynchronous Processing</strong></summary>

- **Why use a message queue?**  
  Decouple services, handle async workloads, buffer spikes.

- **Popular message queues?**  
  Kafka, RabbitMQ, SQS.

- **⚡ How to ensure message delivery?**  
  At-least-once, at-most-once, or exactly-once semantics.

</details>

<details>
<summary><strong>9. API Design & Versioning</strong></summary>

- **REST vs GraphQL?**  
  REST: Fixed endpoints; GraphQL: Client-defined queries.

- **API versioning strategies?**  
  URL versioning (/v1), Header versioning, Query parameter versioning.

- **⚡ What is idempotency?**  
  Multiple identical requests have the same effect as one.

</details>

<details>
<summary><strong>10. Consistency & Availability</strong></summary>

- **CAP Theorem?**  
  A distributed system can guarantee only two of Consistency, Availability, Partition tolerance.

- **Consistency models?**  
  Strong, Eventual, Causal, Read-your-write.

- **⚡ How to maintain availability during partition?**  
  Accept eventual consistency or implement failover strategies.

</details>

<details>
<summary><strong>11. Partitioning & Sharding</strong></summary>

- **What is database sharding?**  
  Splitting database into smaller, faster, manageable parts.

- **Types of sharding?**  
  Horizontal, Vertical, Directory-based, Key-based.

- **⚡ Why use partitioning?**  
  Improve performance and scalability.

</details>

<details>
<summary><strong>12. Rate Limiting</strong></summary>

- **What is rate limiting?**  
  Restrict number of requests per client in a time frame.

- **Common strategies?**  
  Token bucket, Leaky bucket, Fixed window, Sliding window.

</details>

<details>
<summary><strong>13. Monitoring & Logging</strong></summary>

- **Why monitor systems?**  
  Detect issues, track performance, ensure reliability.

- **Popular tools?**  
  Prometheus, Grafana, ELK Stack, Datadog.

- **⚡ Key metrics to monitor?**  
  Latency, throughput, error rates, CPU/memory usage.

</details>

<details>
<summary><strong>14. Security & Authentication</strong></summary>

- **Common auth methods?**  
  OAuth2, JWT, API keys, SAML.

- **⚡ How to secure APIs?**  
  HTTPS, authentication, authorization, input validation.

</details>

<details>
<summary><strong>15. Production-Level Scenarios</strong></summary>

- **⚡ How to handle sudden traffic spikes?**  
  Auto-scaling, queue buffering, CDN, caching.

- **⚡ How to reduce latency?**  
  Caching, DB optimization, CDN, asynchronous processing.

- **⚡ How to ensure high availability?**  
  Load balancing, replication, failover, multi-region deployment.

- **⚡ How to recover from disaster?**  
  Backups, multi-region replication, automated failover.

- **⚡ How to handle data consistency in distributed systems?**  
  Use consensus protocols, replication with quorum, or eventual consistency.

- **⚡ How to debug production issues?**  
  Centralized logging, monitoring alerts, profiling tools.

</details>

<details>
<summary><strong>16. Best Practices</strong></summary>

- Design for scalability from day one.  
- Use caching wisely; avoid cache stampede.  
- Keep services decoupled and stateless when possible.  
- Monitor key metrics and set up alerts.  
- Prefer asynchronous communication for high-load operations.  
- Ensure proper API versioning and backward compatibility.  
- Plan disaster recovery and failover strategies.  
- Optimize database queries and index critical columns.

</details>

<details>
<summary><strong>17. Commands / Tools Cheat Sheet</strong></summary>

- **Load Testing:** `Apache JMeter`, `Locust`, `hey`, `wrk`  
- **Monitoring & Logging:** `Prometheus`, `Grafana`, `ELK Stack`, `Datadog`  
- **Architecture Diagrams:** `draw.io`, `Lucidchart`, `Miro`  
- **Database Optimization:** `EXPLAIN` (MySQL/PostgreSQL), `ANALYZE`, `INDEX` creation  
- **Message Queues:** `kafka-console-producer`, `kafka-console-consumer`, RabbitMQ CLI  

</details>

---

> ⚡ **Tip:** Focus on designing systems that are **scalable, reliable, and maintainable**; interviewers value trade-offs discussion over “perfect” solutions.

