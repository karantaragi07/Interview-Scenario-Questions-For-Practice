# ![Kafka](https://img.shields.io/badge/Apache-Kafka-orange?style=for-the-badge) Apache Kafka Interview Questions & Answers

### **Badges / Tags**
![Kafka](https://img.shields.io/badge/Kafka-Streaming-orange) ![Interview](https://img.shields.io/badge/Interview-Questions-blue) ![ProductionReady](https://img.shields.io/badge/Production-Ready-green)

---

## **Table of Contents**

- [Kafka Basics](#kafka-basics)  
- [Producers & Consumers](#producers--consumers)  
- [Advanced / Production-Level Concepts](#advanced--production-level-concepts)  
- [Monitoring & Troubleshooting](#monitoring--troubleshooting)  
- [Best Practices](#best-practices)  

---

## **Kafka Basics** <a name="kafka-basics"></a>

<details>
<summary>Click to expand Questions & Answers</summary>

**⚡ Q1: What is Kafka?**  
A distributed streaming platform for building real-time data pipelines and applications, allowing reliable publishing, storing, and consuming of messages.  

**Q2: How is Kafka different from a traditional message queue?**  
Kafka stores messages durably and allows multiple consumers to read the same messages; queues remove messages once consumed.  

**⚡ Q3: What is a topic in Kafka?**  
A logical channel for messages where producers send data and consumers read it.  

**Q4: What is a partition in Kafka?**  
A subdivision of a topic that allows parallel processing; message order is guaranteed within a partition.  

**Q5: What is a broker?**  
A Kafka server responsible for storing messages and serving producers and consumers.  

**Q6: What are the main components of Kafka architecture?**  
Producers, consumers, brokers, topics, partitions, consumer groups, and Zookeeper/KRaft for cluster management.  

</details>

---

## **Producers & Consumers** <a name="producers--consumers"></a>

<details>
<summary>Click to expand Questions & Answers</summary>

**⚡ Q7: What is a consumer group?**  
A set of consumers sharing the partitions of a topic for load balancing and scalability.  

**Q8: What happens if the number of consumers exceeds the number of partitions?**  
Extra consumers remain idle, as each partition can only be consumed by one consumer in a group.  

**Q9: How does Kafka track which messages a consumer has read?**  
Through offsets, which can be committed automatically or manually.  

**⚡ Q10: What are the delivery semantics in Kafka?**  
- At-most-once: messages may be lost  
- At-least-once: messages may be duplicated  
- Exactly-once: messages are processed only once  

**Q11: Difference between automatic and manual offset commit?**  
Automatic commit is easier but less reliable; manual commit gives control and reduces duplicate processing.  

**Q12: What is the role of keys in Kafka producers?**  
Keys determine the partition for a message, allowing ordered processing of messages with the same key.  

**Q13: What happens if a consumer fails?**  
Kafka reassigns its partitions to other consumers in the same group.  

</details>

---

## **Advanced / Production-Level Concepts** <a name="advanced--production-level-concepts"></a>

<details>
<summary>Click to expand Questions & Answers</summary>

**⚡ Q14: How does Kafka achieve fault tolerance?**  
Through replication across brokers; leaders handle writes and followers replicate data. Failover occurs automatically.  

**Q15: What is ISR (In-Sync Replicas)?**  
Replicas that are fully caught up with the leader; only ISR members can be promoted to leader.  

**⚡ Q16: When should Kafka be used over REST APIs?**  
Kafka is ideal for asynchronous, high-throughput, durable messaging; REST is suitable for synchronous requests.  

**Q17: What is Kafka Streams?**  
A library to process streams of messages in real-time, enabling transformations, aggregations, and joins.  

**Q18: What is the difference between stateful and stateless processing?**  
- Stateless: no state is maintained across messages  
- Stateful: maintains state such as aggregations or counts across messages  

**⚡ Q19: What is Schema Registry in Kafka?**  
A service to manage message schemas and ensure producer-consumer compatibility.  

**Q20: What are the schema compatibility types?**  
Backward, Forward, and Full.  

**⚡ Q21: What are Kafka transactions?**  
Allow atomic writes to multiple partitions/topics and enable exactly-once processing.  

**Q22: How do you configure a transactional producer?**  
Set `transactional.id`, call `initTransactions()`, wrap sends in `beginTransaction()` and `commitTransaction()`.  

**Q23: How is message order maintained in Kafka?**  
By using a key; messages with the same key are sent to the same partition.  

**Q24: What is consumer lag?**  
The difference between the latest offset and the consumer's offset; indicates if consumers are falling behind.  

**Q25: How can slow producers be handled?**  
Optimize batching, enable compression, and use asynchronous sends.  

**⚡ Q26: What is exactly-once processing?**  
Achieved using idempotent producers, transactions, and committing offsets after processing to ensure messages are processed once.  

**Q27: What are the trade-offs of exactly-once semantics?**  
Adds some performance overhead but ensures correctness in critical systems.  

**Q28: How do you handle message duplication in consumers?**  
Use idempotent operations or track message IDs to avoid duplicate processing.  

**Q29: How do partitions help with scalability?**  
More partitions allow multiple consumers to read in parallel, increasing throughput.  

**Q30: How do producers handle retries?**  
Kafka producers can retry sending messages with `retries` and `acks` settings to ensure reliability.  

</details>

---

## **Monitoring & Troubleshooting** <a name="monitoring--troubleshooting"></a>

<details>
<summary>Click to expand Questions & Answers</summary>

**⚡ Q31: What are common Kafka issues in production?**  
Consumer lag, broker failures, slow producers, disk full, and under-replicated partitions.  

**Q32: How do you monitor Kafka?**  
Using tools like Prometheus, Grafana, and Kafka Manager; monitoring lag, request rates, under-replicated partitions, and disk usage.  

**Q33: What happens if a partition leader fails?**  
An ISR replica is promoted automatically; message order within the partition is preserved.  

**Q34: How do you handle under-replicated partitions?**  
Monitor them and add brokers or adjust replication factor to ensure all replicas are synchronized.  

**Q35: How do you scale Kafka clusters?**  
Increase the number of partitions, add brokers, and balance load across consumer groups.  

</details>

---

## **Best Practices** <a name="best-practices"></a>

<details>
<summary>Click to expand</summary>

- Use **partitions and keys** strategically to maintain message order and enable parallel processing.  
- Monitor **consumer lag** regularly to ensure consumers are keeping up with producers.  
- Configure **replication factor ≥ 3** for fault tolerance and high availability.  
- Use **idempotent producers and transactions** for exactly-once processing.  
- Enable **compression** and **batching** for high throughput and lower network overhead.  
- Use **Schema Registry** to manage schema evolution safely.  
- Regularly monitor **under-replicated partitions**, disk usage, and broker health metrics.  

</details>

---

