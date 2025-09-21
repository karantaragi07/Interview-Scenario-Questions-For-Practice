# RESTful API Interview Preparation

![REST API](https://img.shields.io/badge/REST_API-Interview-blue) ![Interview](https://img.shields.io/badge/Interview-Questions-green) ![Production Ready](https://img.shields.io/badge/Production-Ready-orange)

---

<details>
<summary>📌 Basics</summary>

**Q1: What is a RESTful API?**  
A: RESTful API is an API adhering to REST principles, using HTTP methods to perform CRUD operations.  

⚡ **Q2: What are the key principles of REST?**  
A: Statelessness, Client-Server, Cacheable, Uniform Interface, Layered System, Code on Demand (optional).  

**Q3: Difference between REST and SOAP?**  
A: REST is lightweight, uses JSON/XML, stateless; SOAP is protocol-based, uses XML, and supports WS-* standards.  

**Q4: What is statelessness in REST?**  
A: Each request contains all necessary info; server does not store client state between requests.  

</details>

<details>
<summary>⚡ HTTP Methods</summary>

**Q1: List common HTTP methods and their purpose.**  
A: GET (read), POST (create), PUT (update/replace), PATCH (update/partial), DELETE (delete), OPTIONS (allowed methods), HEAD (headers only).  

**Q2: Difference between PUT and PATCH?**  
A: PUT replaces the resource fully; PATCH updates specific fields only.  

</details>

<details>
<summary>⚡ HTTP Status Codes</summary>

**Q1: Common 2xx codes?**  
A: 200 OK, 201 Created, 204 No Content.  

**Q2: Common 4xx codes?**  
A: 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 409 Conflict.  

**Q3: Common 5xx codes?**  
A: 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable, 504 Gateway Timeout.  

</details>

<details>
<summary>⚡ REST Principles</summary>

**Q1: What is HATEOAS?**  
A: Hypermedia As The Engine Of Application State; responses include links to available actions for the resource.  

**Q2: What is idempotency?**  
A: Multiple identical requests have the same effect as a single request (e.g., PUT, DELETE).  

</details>

<details>
<summary>URI Design</summary>

**Q1: Best practices for RESTful URIs?**  
A: Use nouns, lowercase, hyphens for readability, avoid verbs, version in URI if needed (`/v1/resource`).  

**Q2: Example of a good RESTful URI?**  
A: `/api/v1/users/123/orders`  

</details>

<details>
<summary>Request & Response</summary>

**Q1: What is the difference between query params, path params, and request body?**  
A: Query params filter (`?status=active`), path params identify resources (`/users/1`), request body carries data for POST/PUT/PATCH.  

**Q2: How do you send JSON data in a POST request?**  
A: Set `Content-Type: application/json` and pass JSON in request body.  

</details>

<details>
<summary>JSON & XML</summary>

**Q1: Why JSON is preferred over XML?**  
A: Lightweight, easy to parse, human-readable, widely supported in web APIs.  

**Q2: How do you handle nested JSON in responses?**  
A: Use objects or arrays; ensure API schema is documented.  

</details>

<details>
<summary>Authentication & Authorization (JWT, OAuth)</summary>

⚡ **Q1: Difference between authentication and authorization?**  
A: Authentication verifies identity; authorization checks permissions.  

**Q2: What is JWT?**  
A: JSON Web Token; compact, stateless token used for authentication/authorization.  

**Q3: How does OAuth 2.0 work?**  
A: Client obtains access token via grant types (authorization code, client credentials) to access resources on behalf of user.  

</details>

<details>
<summary>Versioning</summary>

**Q1: Why version an API?**  
A: To maintain backward compatibility while introducing new features.  

**Q2: Common versioning strategies?**  
A: URI versioning (`/v1/users`), header versioning (`Accept: application/vnd.myapi.v1+json`), query param versioning (`?version=1`).  

</details>

<details>
<summary>Pagination & Filtering</summary>

**Q1: How do you paginate results?**  
A: Use `limit` and `offset` or `page` and `size` query parameters.  

**Q2: How to filter results in REST APIs?**  
A: Use query parameters (`/users?status=active&role=admin`).  

</details>

<details>
<summary>Error Handling</summary>

**Q1: How should errors be returned in REST APIs?**  
A: Use proper HTTP status codes and structured response with message, code, timestamp.  

**Q2: Example error response format?**  
A: `{ "error": "Invalid input", "code": 400, "timestamp": "2025-09-21T10:00:00Z" }`  

</details>

<details>
<summary>Rate Limiting</summary>

**Q1: What is rate limiting and why is it important?**  
A: Restricts number of requests per client/time window to prevent abuse and maintain performance.  

**Q2: Common rate-limiting strategies?**  
A: Fixed window, sliding window, token bucket, leaky bucket.  

</details>

<details>
<summary>Caching</summary>

**Q1: How do you cache REST API responses?**  
A: Use HTTP headers (`Cache-Control`, `ETag`, `Last-Modified`) and server-side caching.  

**Q2: Difference between client-side and server-side caching?**  
A: Client-side reduces network calls; server-side reduces server processing.  

</details>

<details>
<summary>Security Best Practices</summary>

⚡ **Q1: How to secure REST APIs?**  
A: Use HTTPS, authentication, authorization, input validation, rate limiting, logging, and avoid exposing sensitive info.  

**Q2: What are common vulnerabilities in REST APIs?**  
A: SQL injection, XSS, CSRF, broken authentication, excessive data exposure.  

</details>

<details>
<summary>Testing & Documentation (Swagger/Postman)</summary>

**Q1: How to test REST APIs?**  
A: Use Postman, cURL, or automated test frameworks (JUnit, RestAssured).  

**Q2: What is Swagger/OpenAPI?**  
A: Tool to document and visualize APIs; provides interactive API docs.  

</details>

<details>
<summary>⚡ Production-Level Scenarios</summary>

**Q1: How to handle high traffic in REST APIs?**  
A: Use load balancers, caching, database indexing, asynchronous processing.  

**Q2: How to reduce latency?**  
A: Optimize queries, use caching, compress payloads, minimize network calls.  

**Q3: How to handle errors gracefully?**  
A: Use consistent error format, retry mechanisms, circuit breakers, logging.  

**Q4: How to prevent security vulnerabilities?**  
A: Input validation, authentication/authorization, HTTPS, security headers, rate limiting.  

**Q5: How to design for scalability?**  
A: Stateless services, horizontal scaling, database sharding/replication, message queues.  

</details>

<details>
<summary>Best Practices</summary>

- Follow **REST principles** and consistent URI design.  
- Keep APIs **stateless**.  
- Use **proper HTTP methods and status codes**.  
- Implement **authentication, authorization, and rate limiting**.  
- **Version APIs** to avoid breaking changes.  
- Use **caching** to improve performance.  
- Provide **clear error messages** and structured responses.  
- Document APIs using **Swagger/OpenAPI**.  
- Optimize for **high traffic and latency**.  
- Always follow **security best practices**.  

</details>

<details>
<summary>Commands / Tools Cheat Sheet</summary>

**cURL Commands:**  
```bash
# GET request
curl -X GET https://api.example.com/users

# POST request with JSON
curl -X POST https://api.example.com/users -H "Content-Type: application/json" -d '{"name":"John"}'

# PUT request
curl -X PUT https://api.example.com/users/1 -H "Content-Type: application/json" -d '{"name":"Jane"}'

# DELETE request
curl -X DELETE https://api.example.com/users/1
```

Postman Tips:

- Use environment variables for base URL and tokens.

- Test GET, POST, PUT, PATCH, DELETE easily.

- Validate responses with tests and scripts.

Common HTTP Headers:

- Content-Type: application/json

- Authorization: Bearer <token>

- Accept: application/json

- Cache-Control: no-cache
</details>
