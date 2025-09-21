# Kubernetes Interview Preparation ⚡

![Kubernetes](https://img.shields.io/badge/Kubernetes-Interview-blue)
![Interview](https://img.shields.io/badge/Questions-Ready-green)
![ProductionReady](https://img.shields.io/badge/Production-Ready-orange)

This repository contains **Kubernetes interview questions and answers** for professionals with 1–2 years of experience.  
All answers are **concise, human-friendly**, and suitable for real-world scenarios.  

---

## Table of Contents
- [Basics](#basics)
- [Orchestration & Scaling](#orchestration--scaling)
- [Services & Networking](#services--networking)
- [Configuration & Secrets](#configuration--secrets)
- [Storage](#storage)
- [Advanced Concepts](#advanced-concepts)
- [Security & RBAC](#security--rbac)
- [Monitoring & Troubleshooting](#monitoring--troubleshooting)
- [Production-Level Scenarios](#production-level-scenarios)
- [Best Practices](#best-practices)
- [kubectl Commands Cheatsheet](#kubectl-commands-cheatsheet)

---

<details>
<summary>Basics</summary>

### ⚡ What is Kubernetes?
Kubernetes is an open-source container orchestration platform for deploying, scaling, and managing containerized applications reliably.

### Key Components
- **Master:** API Server, Scheduler, Controller Manager, etcd.
- **Node:** kubelet, kube-proxy, container runtime.

### ⚡ What is a Pod?
The smallest deployable unit in Kubernetes; can contain one or more containers sharing network and storage.

### Pod vs Container
Containers run inside Pods; Pods are managed by Kubernetes for scaling, networking, and lifecycle.

### ⚡ What is a Deployment?
Manages Pods, ensures desired replicas, supports rolling updates and rollbacks.

### StatefulSet vs Deployment
StatefulSets are for stateful apps needing stable identity and storage; Deployments are for stateless apps.

### DaemonSet
Ensures a copy of a Pod runs on every node (or subset) for node-level services.

### ReplicaSet
Ensures a specified number of pod replicas are running at all times.

### Job & CronJob
- **Job:** Run a task to completion once.  
- **CronJob:** Run jobs on a schedule.

</details>

---

<details>
<summary>Orchestration & Scaling</summary>

### ⚡ How does Kubernetes scale?
- **Manual:** `kubectl scale deployment <name> --replicas=<n>`  
- **Auto:** Horizontal Pod Autoscaler (HPA) based on metrics.

### Horizontal vs Vertical Pod Autoscaling
- Horizontal: Increase/decrease pod count.  
- Vertical: Adjust CPU/memory of pods.

### Rolling Update & Rollback
- Rolling update via Deployment updates image version.  
- Rollback: `kubectl rollout undo deployment <name>`.

### ⚡ Liveness & Readiness Probes
- **Liveness:** Detects and restarts unhealthy containers.  
- **Readiness:** Marks Pods as ready for traffic.

</details>

---

<details>
<summary>Services & Networking</summary>

### ClusterIP, NodePort, LoadBalancer
- **ClusterIP:** Internal access.  
- **NodePort:** Exposed on node IP.  
- **LoadBalancer:** External cloud LB.  

### ⚡ What is an Ingress?
Manages external HTTP/HTTPS access to multiple services, supports routing rules and TLS termination.

### Pod-to-Pod Networking
Pods get unique IPs; CNI plugins (Calico, Flannel) manage networking.

### NetworkPolicies
Control which pods can communicate; deny by default if a policy exists.

</details>

---

<details>
<summary>Configuration & Secrets</summary>

### ConfigMap
Stores non-sensitive config data (env vars, config files).

### Secret
Stores sensitive data (passwords, tokens) encoded in base64.

### Using Secrets
Mount as volume or inject as env vars; access controlled by RBAC.

</details>

---

<details>
<summary>Storage</summary>

### Volume Types
- **emptyDir:** Ephemeral storage.  
- **PersistentVolume (PV):** Actual cluster storage.  
- **PersistentVolumeClaim (PVC):** Pod request for PV.  

### StatefulSets & Storage
StatefulSets retain stable storage using PVs across pod restarts.

### Storage Classes
Enable dynamic provisioning for cloud or networked storage.

</details>

---

<details>
<summary>Advanced Concepts</summary>

### Helm Charts
Package Kubernetes resources for deployment, versioning, and environment-specific configurations.

### Pod Affinity & Anti-Affinity
- Affinity: Pods co-located for performance.  
- Anti-affinity: Pods separated for fault tolerance.

### Namespaces
Isolate cluster resources, manage multi-team environments.

### CI/CD Integration
Use Helm or kubectl in pipelines for dev → staging → prod deployments.

</details>

---

<details>
<summary>Security & RBAC</summary>

### RBAC
Control who can do what using Roles, ClusterRoles, and Bindings.

### ServiceAccounts
Identity for pods to interact with the Kubernetes API.

### Securing Cluster
- Use RBAC, NetworkPolicies, Secrets.  
- Limit API server access.  
- Encrypt etcd at rest.

</details>

---

<details>
<summary>Monitoring & Troubleshooting</summary>

### Logging
Centralized logging via EFK (Elasticsearch, Fluentd, Kibana) or Loki + Grafana.

### Monitoring
Prometheus + Grafana for metrics; Alertmanager for alerts.

### ⚡ Troubleshooting Pods
1. `kubectl describe pod <name>` for events.  
2. `kubectl logs <name>` for container logs.  
3. `kubectl exec -it <pod> -- /bin/bash` for inspection.  
4. Check health probes and dependencies.

### Performance Issues
Check pod/node resource usage, networking, and storage bottlenecks.

</details>

---

<details>
<summary>Production-Level Scenarios</summary>

### ⚡ Resource Management
Set CPU/memory **requests and limits**; use ResourceQuotas to prevent resource starvation.

### Secrets Management
Use Kubernetes Secrets or external vaults; mount only to required pods; encrypt at rest.

### High Availability
Use anti-affinity for critical pods, multi-node clusters, and replica sets for redundancy.

### Disaster Recovery
- Backup etcd and PVs regularly.  
- Multi-cluster or cross-region setups for failover.  
- Test recovery procedures periodically.

### Logging & Monitoring
Centralized logging, Prometheus/Grafana, liveness/readiness probes, and alerts for proactive issue resolution.

### CI/CD & Rollouts
Use Helm or kubectl for automated, repeatable deployments; rolling updates with rollback support.

### Networking
NetworkPolicies to restrict communication; Ingress for flexible routing; ensure DNS and CNI are working correctly.

### Troubleshooting Example
- Pod CrashLoopBackOff → check logs, probes, env vars, and dependencies.  
- Performance degradation → inspect metrics, scale pods, optimize resource allocation.

</details>

---

<details>
<summary>Best Practices</summary>

- Always define **resource requests and limits** for production workloads.  
- Use **readiness and liveness probes** for pod health checks.  
- Use **Namespaces and RBAC** for isolation and access control.  
- Keep **configuration and secrets separate** from images.  
- Use **Helm or Kustomize** for environment-specific deployments.  
- Monitor and alert using **Prometheus + Grafana**.  
- Regularly **backup etcd and PVs** for disaster recovery.  
- Prefer **anti-affinity and replica sets** for high availability.  
- Test rollouts and rollbacks before production deployment.

</details>

---

<details>
<summary>kubectl Commands Cheatsheet</summary>

### Pods
- List pods: `kubectl get pods`
- Describe pod: `kubectl describe pod <pod-name>`
- View logs: `kubectl logs <pod-name>`
- Exec into pod: `kubectl exec -it <pod-name> -- /bin/bash`
- Delete pod: `kubectl delete pod <pod-name>`

### Deployments
- Create deployment: `kubectl create deployment <name> --image=<image>`
- Update deployment image: `kubectl set image deployment/<name> <container>=<image>`
- Scale deployment: `kubectl scale deployment <name> --replicas=<n>`
- Rolling update: `kubectl rollout status deployment/<name>`
- Rollback: `kubectl rollout undo deployment/<name>`

### Services
- List services: `kubectl get svc`
- Expose deployment: `kubectl expose deployment <name> --type=<ClusterIP|NodePort|LoadBalancer> --port=<port>`

### ConfigMaps & Secrets
- Create ConfigMap: `kubectl create configmap <name> --from-literal=<key>=<value>`
- Create Secret: `kubectl create secret generic <name> --from-literal=<key>=<value>`
- View ConfigMaps: `kubectl get configmap`
- View Secrets: `kubectl get secret`

### Namespaces
- List namespaces: `kubectl get ns`
- Create namespace: `kubectl create namespace <name>`
- Run pod in namespace: `kubectl run <pod> --image=<image> -n <namespace>`

### Scaling & Autoscaling
- Horizontal Pod Autoscaler: `kubectl autoscale deployment <name> --cpu-percent=<value> --min=<n> --max=<n>`
- Check HPA: `kubectl get hpa`

### Persistent Volumes
- List PVs: `kubectl get pv`
- List PVCs: `kubectl get pvc`

### Jobs & CronJobs
- Create Job: `kubectl create job <name> --image=<image>`
- Create CronJob: `kubectl create cronjob <name> --image=<image> --schedule="<cron-schedule>"`
- List jobs/cronjobs: `kubectl get jobs` / `kubectl get cronjobs`

### Node & Cluster
- List nodes: `kubectl get nodes`
- Describe node: `kubectl describe node <node-name>`
- Cluster info: `kubectl cluster-info`

### Logs & Debugging
- Stream logs: `kubectl logs -f <pod-name>`
- Top pods: `kubectl top pod`
- Top nodes: `kubectl top node`

</details>
