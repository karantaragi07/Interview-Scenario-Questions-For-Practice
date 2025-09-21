# Docker Interview Questions & Answers

![Docker](https://img.shields.io/badge/Docker-Container-blue) ![Interview](https://img.shields.io/badge/Interview-Questions-green) ![Production Ready](https://img.shields.io/badge/Production-Ready-orange)

A comprehensive list of **Docker interview questions and answers** for professionals with 1–2 years of experience. ⚡ indicates **high-priority questions**. Includes **production-level scenarios and troubleshooting**.

---

<details>
<summary><strong>1. Basics</strong></summary>

**⚡ What is Docker?**  
Docker is a platform for containerizing applications, bundling code and dependencies into portable containers.

**⚡ What is a Docker Container?**  
A container is a lightweight, isolated runtime instance of a Docker image.

**⚡ What is a Docker Image?**  
A read-only template that contains app code, dependencies, and configuration.

**Dockerfile:**  
A text file with step-by-step instructions to build a Docker image.

**⚡ Docker Engine:**  
Core component that manages images, containers, networks, and volumes (daemon + CLI + REST API).

**Docker Runtime:**  
Low-level software (e.g., `runc`) that actually executes containers.

**Docker Registry:**  
Stores and distributes Docker images, e.g., Docker Hub, AWS ECR.

**Docker Compose:**  
Tool for defining and running multi-container applications with a YAML file.

**Volume:**  
Persistent storage that lives outside the container lifecycle.

**Networking:**  
Enables container-to-container and container-to-host communication.

**⚡ Difference between Container and VM:**  
Containers share the host OS and are lightweight; VMs include a full OS and are heavier.

**What is multi-stage build?**  
Used to reduce image size by separating build and runtime stages in Dockerfile.

**What is a layered filesystem?**  
Each Dockerfile instruction creates a layer; layers are cached and reused.

</details>

<details>
<summary><strong>2. Docker Commands & Operations</strong></summary>

**⚡ How to run a Docker container?**  
`docker run -p 8080:8080 <image_name>`

**List running containers:**  
`docker ps`

**Stop a container:**  
`docker stop <container_id>`

**Remove a container:**  
`docker rm <container_id>`

**Build an image from Dockerfile:**  
`docker build -t <image_name>:<tag> .`

**Pull an image from registry:**  
`docker pull <image_name>`

**Push image to registry:**  
`docker push <username>/<image_name>:<tag>`

**Port Conflict Scenario:**  
If `docker run -p 8080:8080` fails:  
- `lsof -i :8080` to find process  
- Run on a different host port `-p 9090:8080`  
- Stop the conflicting service

**View container logs:**  
`docker logs <container_id>`

**Inspect container details:**  
`docker inspect <container_id>`

**Clean up unused resources:**  
`docker system prune`

**Commit container to image:**  
`docker commit <container_id> <new_image_name>`

**Restart policies:**  
`--restart=always` ensures container auto-restarts in production.

</details>

<details>
<summary><strong>3. Dockerfile & Build</strong></summary>

**⚡ Difference between CMD and ENTRYPOINT:**  
CMD provides default arguments; ENTRYPOINT sets executable. CMD can be overridden at runtime.

**Difference between COPY and ADD:**  
COPY copies files; ADD can also extract tar files and fetch from URLs.

**EXPOSE vs -p flag:**  
EXPOSE declares container port; `-p` maps it to host port.

**Optimize image size:**  
Use multi-stage builds, small base images, and remove unnecessary files.

**Build cache:**  
Docker reuses layers to speed up builds unless instruction changes.

</details>

<details>
<summary><strong>4. Networking & Storage</strong></summary>

**Docker Network Types:**  
bridge (default), host, none, overlay, macvlan.

**Inter-container communication:**  
Use networks and aliases to allow containers to talk to each other.

**Bind mounts vs Volumes vs tmpfs:**  
- Bind mount: host path → container  
- Volume: managed by Docker  
- tmpfs: in-memory storage

**Port mapping:**  
`docker run -p <host_port>:<container_port>` maps container port to host.

**Backup & restore volumes:**  
`docker run --rm -v volume_name:/data busybox tar cvf /backup.tar /data`

</details>

<details>
<summary><strong>5. Security</strong></summary>

**Run container as non-root:**  
Use `USER` in Dockerfile for safer execution.

**Docker Content Trust (DCT):**  
Ensures images are signed and verified.

**Scan images for vulnerabilities:**  
Use Trivy, Clair, or Snyk before deploying.

**Secrets management:**  
Use Docker secrets or environment variables instead of hardcoding credentials.

**Resource limits:**  
Use `--memory` and `--cpus` to prevent resource hogging.

</details>

<details>
<summary><strong>6. CI/CD & DevOps</strong></summary>

**Docker in CI/CD pipelines:**  
Use Docker to build, test, and deploy consistent images across environments.

**Environment variables & .env files:**  
Pass configs securely to containers; `.env` is supported in Docker Compose.

**Rolling updates & blue-green deployment:**  
Used to update services without downtime in production.

**Integration with orchestration tools:**  
Containers deployed via Kubernetes or Swarm for scaling and self-healing.

**⚡ Logging & monitoring integration:**  
Send container logs to ELK/Prometheus/Grafana for production observability.

</details>

<details>
<summary><strong>7. Orchestration & Scaling</strong></summary>

**Difference: Pod vs Container (Kubernetes):**  
A Pod can contain one or more containers; Pod is the deployment unit.

**Replicas & scaling:**  
Increase or decrease container instances to handle traffic.

**Health checks:**  
Use liveness/readiness probes in K8s or HEALTHCHECK in Dockerfile.

**Load balancing:**  
Managed via orchestration tools; routes traffic across multiple containers.

**Secrets & configs in Swarm/K8s:**  
Store sensitive data securely and inject at runtime.

</details>

<details>
<summary><strong>8. Monitoring & Troubleshooting (Production-Level)</strong></summary>

**Monitor resources:**  
`docker stats` for CPU/memory usage.

**View events:**  
`docker events` to track container lifecycle.

**Container exiting immediately:**  
Check entrypoint/command errors or missing dependencies.

**Memory/CPU limits:**  
Prevent container hogging; use `--memory`, `--cpus`.

**Crash recovery:**  
Use `--restart=always` or orchestration self-healing.

**Secrets/config issues:**  
Check env variables, mounted configs, or Docker secrets.

**Scaling issues:**  
Use orchestration for replica management; verify network connectivity.

**Disk cleanup & unused images:**  
`docker system prune` to free space safely.

**Image vulnerabilities:**  
Scan images before production deployment with Trivy/Snyk.

</details>

<details>
<summary><strong>9. Best Practices</strong></summary>

- Use small, official base images.  
- Keep containers stateless; persist data in volumes.  
- Pin image versions; avoid `latest` in production.  
- Multi-stage builds to reduce size.  
- Security scanning before production deployment.  
- Use Docker Compose for local dev; orchestration for production.  
- Integrate with CI/CD pipelines for automated builds and deployments.  
- Monitor containers and logs proactively.  
- Set resource limits and restart policies.  
- Keep secrets and credentials out of Dockerfiles.  

</details>

<details>
<summary><strong>10. Docker Commands Cheat Sheet</strong></summary>

### 🔹 Container Management
- Run container: `docker run -p 8080:8080 <image_name>`  
- List running containers: `docker ps`  
- Stop container: `docker stop <container_id>`  
- Remove container: `docker rm <container_id>`  
- Inspect container: `docker inspect <container_id>`  
- View logs: `docker logs <container_id>`  
- Restart container: `docker restart <container_id>`  
- Commit container to image: `docker commit <container_id> <new_image_name>`  

### 🔹 Image Management
- Build image from Dockerfile: `docker build -t <image_name>:<tag> .`  
- List images: `docker images`  
- Pull image: `docker pull <image_name>`  
- Push image: `docker push <username>/<image_name>:<tag>`  
- Remove image: `docker rmi <image_name>`  
- Tag image: `docker tag <image_name> <username>/<image_name>:<tag>`  

### 🔹 Volumes & Storage
- Create volume: `docker volume create <volume_name>`  
- List volumes: `docker volume ls`  
- Remove volume: `docker volume rm <volume_name>`  
- Run container with volume: `docker run -v <volume_name>:/data <image_name>`  

### 🔹 Networking
- List networks: `docker network ls`  
- Create network: `docker network create <network_name>`  
- Connect container to network: `docker network connect <network_name> <container_name>`  
- Disconnect container: `docker network disconnect <network_name> <container_name>`  

### 🔹 System & Cleanup
- Disk cleanup: `docker system prune`  
- Remove all stopped containers: `docker container prune`  
- Remove all unused images: `docker image prune`  
- Remove all unused volumes: `docker volume prune`  
- View Docker events: `docker events`  
- Monitor containers: `docker stats`  

</details>

---

> ⚡ **Tip:** Focus on **containers, images, Dockerfile, Compose, orchestration, CI/CD, production troubleshooting, security, and commands** 
