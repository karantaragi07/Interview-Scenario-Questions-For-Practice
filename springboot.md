# ![Spring Boot](https://img.shields.io/badge/Spring-Boot-brightgreen?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Questions-blue?style=for-the-badge) ![Production Ready](https://img.shields.io/badge/Production-Ready-orange?style=for-the-badge)

# Spring Boot Interview Questions & Answers

---

## Table of Contents
1. [Basics](#basics)
2. [Spring Boot Annotations](#spring-boot-annotations)
3. [Spring MVC & REST APIs](#spring-mvc--rest-apis)
4. [Dependency Injection](#dependency-injection)
5. [Spring Data JPA](#spring-data-jpa)
6. [Spring Security](#spring-security)
7. [Exception Handling](#exception-handling)
8. [Actuator & Monitoring](#actuator--monitoring)
9. [Testing](#testing)
10. [Spring Profiles & Configuration](#spring-profiles--configuration)
11. [Microservices](#microservices)
12. [Spring Boot CLI / Commands](#spring-boot-cli--commands)
13. [Production-Level Scenarios](#production-level-scenarios)
14. [Best Practices](#best-practices)

---

<details>
<summary><strong>Basics</strong></summary>

- **What is Spring Boot?**  
  Spring Boot is a framework on top of Spring that simplifies setup with auto-configuration, embedded servers, and starter dependencies.

- **⚡ Difference between Spring and Spring Boot?**  
  Spring Boot reduces boilerplate setup and provides production-ready features; Spring is the core framework.

- **What are Spring Boot Starters?**  
  Predefined dependency sets that simplify adding libraries like Web, JPA, Security without manual configuration.

- **What is auto-configuration?**  
  Spring Boot automatically configures beans based on classpath and defined beans; can be overridden with custom beans.

- **What are Spring Boot Profiles?**  
  Profiles separate configurations for different environments (`dev`, `test`, `prod`) using `application-{profile}.yml`.

</details>

<details>
<summary><strong>Spring Boot Annotations</strong></summary>

- **@SpringBootApplication**: Combines `@Configuration`, `@EnableAutoConfiguration`, and `@ComponentScan`.  
- **@RestController**: Marks a class as a REST API controller; combines `@Controller` + `@ResponseBody`.  
- **@Service / @Repository / @Component**: Marks beans for DI; `@Service` for service logic, `@Repository` for DB layer.  
- **@Autowired**: Injects dependencies automatically. Prefer constructor injection for immutability.  
- **@Transactional**: Manages database transactions; rolls back on exceptions.

</details>

<details>
<summary><strong>Spring MVC & REST APIs</strong></summary>

- **Difference between @Controller and @RestController?**  
  `@RestController` returns JSON by default; `@Controller` returns views.  

- **How to handle exceptions in REST APIs?**  
  Use `@RestControllerAdvice` with `@ExceptionHandler` for global exception handling.  

- **⚡ How to make REST APIs stateless?**  
  Don’t store session state on server; use JWT or client-side tokens.  

</details>

<details>
<summary><strong>Dependency Injection</strong></summary>

- **What is dependency injection?**  
  Spring injects beans into classes rather than creating objects manually.  

- **Constructor vs Field Injection?**  
  Constructor injection is preferred for immutability and easier testing; field injection couples the class to Spring.  

</details>

<details>
<summary><strong>Spring Data JPA</strong></summary>

- **Difference between CrudRepository & JpaRepository?**  
  JpaRepository extends CrudRepository; adds methods for pagination and sorting.  

- **Lazy vs Eager fetching?**  
  Lazy loads related entities on access; Eager loads immediately. Lazy preferred to avoid unnecessary DB calls.  

- **⚡ How does @Transactional work?**  
  Starts a transaction at method entry, commits if successful, rolls back on exceptions.  

</details>

<details>
<summary><strong>Spring Security</strong></summary>

- **How to secure REST APIs?**  
  Use Spring Security with JWT for stateless authentication.  

- **How to restrict endpoints?**  
  Use `.authorizeHttpRequests()` in security config with `.permitAll()`, `.hasRole("ADMIN")`, etc.  

- **Difference between authentication and authorization?**  
  Authentication: Verify identity; Authorization: Check access rights.  

</details>

<details>
<summary><strong>Exception Handling</strong></summary>

- **Global exception handling?**  
  `@RestControllerAdvice` with `@ExceptionHandler` handles exceptions across controllers.  

- **Custom error response?**  
  Create POJO for error details and return it in `@ExceptionHandler` methods.  

</details>

<details>
<summary><strong>Actuator & Monitoring</strong></summary>

- **What is Spring Boot Actuator?**  
  Provides endpoints for health, metrics, and monitoring.  

- **⚡ Common endpoints?**  
  `/actuator/health`, `/actuator/metrics`, `/actuator/env`.  

- **Custom actuator endpoints?**  
  Implement `@Endpoint` or extend `AbstractEndpoint` to expose custom metrics.  

</details>

<details>
<summary><strong>Testing</strong></summary>

- **Unit vs Integration testing?**  
  Unit: Test single classes using JUnit & Mockito.  
  Integration: Load Spring context with `@SpringBootTest` to test real flows.  

- **Test REST APIs?**  
  Use `MockMvc` to simulate HTTP requests and validate responses.  

</details>

<details>
<summary><strong>Spring Profiles & Configuration</strong></summary>

- **Managing multiple environments?**  
  Use `application-{profile}.yml` files and activate with `spring.profiles.active`.  

- **Secure sensitive info?**  
  Use environment variables, secret managers, or Kubernetes Secrets.  

</details>

<details>
<summary><strong>Microservices</strong></summary>

- **Communication methods?**  
  REST (synchronous) and Kafka (asynchronous, event-driven).  

- **REST vs Kafka?**  
  REST: Direct request-response.  
  Kafka: Decoupled, scalable, eventual consistency.  

- **Service discovery?**  
  Use Eureka or Kubernetes service registry for dynamic endpoints.  

</details>

<details>
<summary><strong>Spring Boot CLI / Commands</strong></summary>

- **Run project:** `mvn spring-boot:run`  
- **Package JAR:** `mvn clean package`  
- **Run JAR:** `java -jar target/app-name.jar`  
- **Run with profile:** `java -jar target/app.jar --spring.profiles.active=prod`  
- **Build Docker image:** `docker build -t app-name .`  
- **Run container:** `docker run -p 8080:8080 app-name`  

</details>

<details>
<summary><strong>Production-Level Scenarios</strong></summary>

- **Performance issues?**  
  Use Actuator metrics, profile code, optimize DB queries, add caching.  

- **Memory leaks / OOM?**  
  Heap dumps, profilers, fix heavy objects or unclosed resources.  

- **Scaling?**  
  Horizontal scaling with load balancer; tune thread pools and DB connections.  

- **Resilience?**  
  Circuit breakers, retries, fallbacks, timeouts using Resilience4j.  

- **Centralized logging & tracing?**  
  ELK / EFK stack; Spring Cloud Sleuth + Zipkin for distributed tracing.  

- **Database migrations?**  
  Use Flyway or Liquibase to manage schema versions.  

- **Monitoring & health checks?**  
  Actuator health, custom health indicators, integrate with Prometheus/Grafana.  

</details>

<details>
<summary><strong>Best Practices</strong></summary>

- Use constructor injection over field injection.  
- Enable profiles for environment-specific configs.  
- Use caching for expensive DB calls.  
- Always implement global exception handling.  
- Externalize sensitive configs using env variables or secret managers.  
- Implement monitoring, logging, and health checks for production apps.  
- Containerize apps with lightweight images and proper health checks.  
- Apply resilience patterns (circuit breaker, retries) for microservices.  

</details>
