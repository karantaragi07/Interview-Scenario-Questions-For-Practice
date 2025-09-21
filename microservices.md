# ![Microservices](https://img.shields.io/badge/Microservices-Architecture-blue?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Questions-green?style=for-the-badge) ![ProductionReady](https://img.shields.io/badge/Production-Ready-orange?style=for-the-badge)
 

---

## 📌 Table of Contents
- [Basics](#basics)
- [Architecture](#architecture)
- [Communication (REST/gRPC)](#communication-restgrpc)
- [Service Discovery](#service-discovery)
- [Load Balancing](#load-balancing)
- [API Gateway](#api-gateway)
- [Circuit Breaker & Resilience](#circuit-breaker--resilience)
- [Distributed Transactions & Event-Driven Architecture](#distributed-transactions--event-driven-architecture)
- [Messaging (Kafka/RabbitMQ)](#messaging-kafkarabbitmq)
- [Database per Service](#database-per-service)
- [Versioning](#versioning)
- [Monitoring & Logging](#monitoring--logging)
- [Security](#security)
- [CI/CD](#cicd)
- [Containerization & Orchestration](#containerization--orchestration)
- [Production-Level Questions](#production-level-questions)
- [Best Practices](#best-practices)
- [Commands / Tools Cheat Sheet](#commands--tools-cheat-sheet)

---

<details>
<summary>💡 Basics</summary>

**Q:** ⚡ What are Microservices?  
**A:** Independent services for specific business functions, loosely coupled and deployable separately.  

**Q:** Microservices vs Monolith?  
**A:** Monolith: single deployable app; Microservices: small independent services, scalable and flexible.  

**Q:** Benefits of Microservices?  
**A:** Independent deployment, scalability, fault isolation, faster development, technology flexibility.  

</details>

<details>
<summary>🏗 Architecture</summary>

**Q:** Database per service?  
**A:** Each service owns its database to ensure loose coupling.  

**Q:** How to handle data consistency?  
**A:** Eventual consistency using Saga pattern or event-driven architecture.  

**Q:** Saga pattern?  
**A:** Break transaction into local steps; use compensating actions on failure.  

</details>

<details>
<summary>🔗 Communication (REST/gRPC)</summary>

**Q:** How do services communicate?  
**A:** Synchronous (REST/gRPC) or asynchronous (Kafka/RabbitMQ).  

**Q:** When use Kafka over REST?  
**A:** High-throughput async processing; REST may fail under load.  

</details>

<details>
<summary>🔍 Service Discovery</summary>

**Q:** What is Service Discovery?  
**A:** Dynamically find and communicate with services; avoids hardcoding URLs.  

**Q:** Client-side vs Server-side discovery?  
**A:** Client-side: client queries registry; Server-side: load balancer routes requests.  

</details>

<details>
<summary>⚖️ Load Balancing</summary>

**Q:** How to load balance services?  
**A:** Distribute requests among instances using client-side (Ribbon) or server-side (NGINX, Gateway).  

**Q:** Horizontal vs Vertical scaling?  
**A:** Horizontal: add instances (preferred); Vertical: increase resources on single instance.  

</details>

<details>
<summary>🛡 API Gateway</summary>

**Q:** What is API Gateway?  
**A:** Single entry point for routing, aggregation, authentication, logging, rate-limiting.  

**Q:** Popular tools?  
**A:** Spring Cloud Gateway, Netflix Zuul, Kong, AWS API Gateway.  

</details>

<details>
<summary>⚡ Circuit Breaker & Resilience</summary>

**Q:** How to ensure resiliency?  
**A:** Circuit breaker, retries with backoff, timeouts, fallback, bulkhead pattern.  

**Q:** Circuit Breaker explained?  
**A:** Stops requests to failing service temporarily, prevents cascading failures.  

</details>

<details>
<summary>💾 Distributed Transactions & Event-Driven Architecture</summary>

**Q:** Distributed transaction strategies?  
**A:** Saga pattern, event-driven updates; avoid 2-phase commit in microservices.  

**Q:** Event-driven architecture?  
**A:** Services emit events after DB updates; others react asynchronously.  

</details>

<details>
<summary>📩 Messaging (Kafka/RabbitMQ)</summary>

**Q:** Kafka reliability?  
**A:** Use replication, acks, idempotent consumers, monitor consumer lag.  

**Q:** Dead-letter queue?  
**A:** Stores failed messages for later inspection and reprocessing.  

**Q:** At-least-once vs exactly-once delivery?  
**A:** At-least-once: may duplicate; exactly-once: processed only once.  

</details>

<details>
<summary>🗄 Database per Service</summary>

**Q:** Benefits?  
**A:** Loose coupling, service autonomy, easier scaling and maintenance.  

**Q:** Challenges?  
**A:** Maintaining consistency, joins across databases, distributed transactions.  

</details>

<details>
<summary>🆕 Versioning</summary>

**Q:** How to version APIs?  
**A:** URI versioning (`/v1/orders`), header versioning, or query parameter versioning.  

**Q:** Multiple client versions?  
**A:** Maintain concurrent versions, deprecate gradually, route via API Gateway.  

</details>

<details>
<summary>📊 Monitoring & Logging</summary>

**Q:** Tools for monitoring?  
**A:** Prometheus + Grafana, Spring Boot Actuator.  

**Q:** Centralized logging?  
**A:** ELK Stack (Elasticsearch, Logstash, Kibana) or Splunk.  

**Q:** Distributed tracing?  
**A:** Track a request across multiple services using Jaeger or Zipkin.  

</details>

<details>
<summary>🔒 Security</summary>

**Q:** How to secure microservices?  
**A:** JWT/OAuth2 for APIs, HTTPS/mTLS for inter-service, RBAC.  

**Q:** JWT usage?  
**A:** Auth service issues token; each service validates locally for stateless auth.  

</details>

<details>
<summary>🚀 CI/CD</summary>

**Q:** CI/CD for microservices?  
**A:** Build, test, push Docker images, deploy via Kubernetes, monitor health.  

**Q:** Rollback strategy?  
**A:** Keep previous Docker image; Kubernetes rollbacks if deployment fails.  

</details>

<details>
<summary>🐳 Containerization & Orchestration</summary>

**Q:** Docker & Kubernetes in microservices?  
**A:** Docker packages service; K8s manages pods, deployments, services, ingress.  

**Q:** Zero-downtime deployment?  
**A:** Rolling updates gradually replace pods without downtime.  

</details>

<details>
<summary>⚡ Production-Level Questions</summary>

**Q:** High load causing service failure?  
**A:** Horizontal scaling, caching, async processing, rate-limiting.  

**Q:** Latency in multi-service flow?  
**A:** Use distributed tracing, optimize slow services, batch DB calls.  

**Q:** Message failures in Kafka?  
**A:** Retry, dead-letter queue, idempotent consumers, monitor broker health.  

**Q:** Data inconsistency?  
**A:** Saga pattern, event-driven updates, compensating transactions.  

**Q:** Service unavailable intermittently?  
**A:** Circuit breaker, retries, fallback, monitor metrics/logs, scale service.  

**Q:** Logging/monitoring in production?  
**A:** Centralized logging, metrics dashboards, distributed tracing, alerting.  

</details>

<details>
<summary>✅ Best Practices</summary>

- Design services **loosely coupled and single-responsibility**.  
- Use **API Gateway** for routing, auth, logging.  
- Implement **resilience patterns**: circuit breaker, fallback, retries.  
- Adopt **event-driven async communication** for heavy workloads.  
- **Monitor & log centrally**; use distributed tracing.  
- **Version APIs** properly; maintain backward compatibility.  
- **Automate CI/CD**; enable zero-downtime deployment.  
- Containerize services and orchestrate via **Kubernetes**.  
- Ensure **security** at API and inter-service levels.  

</details>

<details>
<summary>🛠 Commands / Tools Cheat Sheet</summary>

**Docker:**  
```bash
docker build -t service-name .
docker run -p 8080:8080 service-name
docker ps
docker logs <container-id>
```
**Kubernetes:**
```
kubectl apply -f deployment.yaml
kubectl get pods
kubectl get svc
kubectl describe pod <pod-name>
kubectl rollout status deployment <deployment-name>
kubectl rollout undo deployment <deployment-name>
```
**Spring Boot:**
```
mvn clean install
mvn spring-boot:run
java -jar target/app.jar
```
**Kafka:**
```
kafka-topics.sh --create --topic test --bootstrap-server localhost:9092
kafka-console-producer.sh --topic test --bootstrap-server localhost:9092
kafka-console-consumer.sh --topic test --bootstrap-server localhost:9092 --from-beginning
```
**Postman:**
```
Send REST API requests, test endpoints, save collections.
```
</details>
