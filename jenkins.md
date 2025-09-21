# ![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-blue?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Questions-green?style=for-the-badge) ![Production Ready](https://img.shields.io/badge/Production-Ready-orange?style=for-the-badge)

# Jenkins Interview Questions & Answers

---

## 📂 Table of Contents
1. [Basics](#basics)
2. [Jenkins Architecture](#jenkins-architecture)
3. [Pipelines (Declarative & Scripted)](#pipelines-declarative--scripted)
4. [Jobs & Builds](#jobs--builds)
5. [Plugins](#plugins)
6. [SCM Integration (Git)](#scm-integration-git)
7. [Build Triggers](#build-triggers)
8. [Nodes & Executors](#nodes--executors)
9. [Jenkinsfile](#jenkinsfile)
10. [Parameters](#parameters)
11. [Credentials & Secrets](#credentials--secrets)
12. [Monitoring & Logging](#monitoring--logging)
13. [Production-Level Scenarios](#production-level-scenarios)
14. [Best Practices](#best-practices)
15. [Commands / Tools Cheat Sheet](#commands--tools-cheat-sheet)

---

## <a name="basics"></a>📌 Basics
<details>
<summary>Click to expand Basics Q&A</summary>

**⚡Q1: What is Jenkins?**  
A: Jenkins is an open-source automation server used for CI/CD pipelines.

**Q2: What is Continuous Integration (CI)?**  
A: CI is the practice of merging code frequently to detect issues early.

**Q3: What is Continuous Delivery (CD)?**  
A: CD automates software delivery to production or staging environments.

**Q4: What are the advantages of Jenkins?**  
A: Open-source, extensible with plugins, easy setup, supports distributed builds.

**Q5: What is a Jenkins Job?**  
A: A job defines tasks like building, testing, or deploying an application.

</details>

---

## <a name="jenkins-architecture"></a>📌 Jenkins Architecture
<details>
<summary>Click to expand Architecture Q&A</summary>

**⚡Q1: Explain Jenkins architecture.**  
A: Jenkins uses a master-agent model: the master schedules jobs, agents execute them.

**Q2: What is the role of the Jenkins Master?**  
A: Master handles job scheduling, monitoring, and storing build artifacts.

**Q3: What is a Jenkins Agent (Node)?**  
A: Agent executes jobs delegated by the master on different environments.

**Q4: How does distributed builds work?**  
A: Multiple agents run jobs in parallel to speed up CI/CD pipelines.

</details>

---

## <a name="pipelines-declarative--scripted"></a>📌 Pipelines (Declarative & Scripted)
<details>
<summary>Click to expand Pipelines Q&A</summary>

**⚡Q1: What is a Jenkins Pipeline?**  
A: Pipeline is code defining the complete CI/CD workflow.

**Q2: Difference between Declarative & Scripted Pipeline?**  
A: Declarative: structured, simple syntax; Scripted: flexible Groovy-based code.

**Q3: What are stages and steps?**  
A: Stage: major pipeline segment; Step: single task inside a stage.

**Q4: How do you handle errors in pipelines?**  
A: Use `try-catch`, `post` section with `always`, `success`, or `failure`.

</details>

---

## <a name="jobs--builds"></a>📌 Jobs & Builds
<details>
<summary>Click to expand Jobs & Builds Q&A</summary>

**⚡Q1: What types of Jenkins jobs exist?**  
A: Freestyle, Pipeline, Multibranch Pipeline, GitHub Organization, Matrix.

**Q2: What is a build?**  
A: Execution of a job producing artifacts or reports.

**Q3: How to view build history?**  
A: Use Jenkins UI under “Build History” or REST API.

**Q4: How to trigger a build manually?**  
A: Click **Build Now** in the Jenkins job page.

</details>

---

## <a name="plugins"></a>📌 Plugins
<details>
<summary>Click to expand Plugins Q&A</summary>

**⚡Q1: What are Jenkins plugins?**  
A: Plugins extend Jenkins features like SCM, notifications, and pipelines.

**Q2: How to install a plugin?**  
A: Manage Jenkins → Manage Plugins → Available → Install.

**Q3: Name important plugins for CI/CD.**  
A: Git, Pipeline, GitHub, Blue Ocean, Slack Notification, Docker.

</details>

---

## <a name="scm-integration-git"></a>📌 SCM Integration (Git)
<details>
<summary>Click to expand SCM Q&A</summary>

**⚡Q1: How to integrate Git with Jenkins?**  
A: Use Git plugin and configure repository URL and credentials in the job.

**Q2: How to trigger builds on Git push?**  
A: Enable webhooks in GitHub/GitLab and configure SCM polling.

**Q3: How to handle branch-specific builds?**  
A: Use Multibranch Pipeline or specify branches in job configuration.

</details>

---

## <a name="build-triggers"></a>📌 Build Triggers
<details>
<summary>Click to expand Build Triggers Q&A</summary>

**⚡Q1: What are Jenkins build triggers?**  
A: Conditions that automatically start a build, e.g., SCM changes or schedules.

**Q2: How to schedule a job?**  
A: Use CRON syntax in the “Build Triggers → Build periodically” section.

**Q3: How to trigger downstream jobs?**  
A: Use “Build other projects” or `build job:` in pipeline scripts.

</details>

---

## <a name="nodes--executors"></a>📌 Nodes & Executors
<details>
<summary>Click to expand Nodes & Executors Q&A</summary>

**⚡Q1: What is a Jenkins node?**  
A: Any machine (master/agent) that can execute Jenkins jobs.

**Q2: What is an executor?**  
A: An executor is a slot on a node that runs a single job at a time.

**Q3: How to add a new node?**  
A: Manage Jenkins → Manage Nodes → New Node → Configure.

</details>

---

## <a name="jenkinsfile"></a>📌 Jenkinsfile
<details>
<summary>Click to expand Jenkinsfile Q&A</summary>

**⚡Q1: What is Jenkinsfile?**  
A: A file storing pipeline code, versioned with the project.

**Q2: Benefits of Jenkinsfile?**  
A: Version control, code review, reproducible pipelines, better CI/CD.

**Q3: How to define environment variables?**  
A: Use `environment { VAR_NAME = "value" }` inside Declarative Pipeline.

</details>

---

## <a name="parameters"></a>📌 Parameters
<details>
<summary>Click to expand Parameters Q&A</summary>

**⚡Q1: What are Jenkins parameters?**  
A: Input values that modify job behavior at build time.

**Q2: Types of parameters?**  
A: String, Boolean, Choice, Password, File, etc.

**Q3: How to access parameter values in pipeline?**  
A: Use `params.PARAM_NAME`.

</details>

---

## <a name="credentials--secrets"></a>📌 Credentials & Secrets
<details>
<summary>Click to expand Credentials Q&A</summary>

**⚡Q1: How does Jenkins handle secrets?**  
A: Use **Credentials plugin** to store passwords, tokens, SSH keys securely.

**Q2: How to use credentials in pipelines?**  
A: Use `withCredentials` block for environment variables.

</details>

---

## <a name="monitoring--logging"></a>📌 Monitoring & Logging
<details>
<summary>Click to expand Monitoring Q&A</summary>

**Q1: How to monitor Jenkins?**  
A: Use built-in Dashboard, Blue Ocean, or external tools like Prometheus.

**Q2: How to access Jenkins logs?**  
A: Jenkins home → `logs` directory or **Manage Jenkins → System Log**.

**Q3: How to troubleshoot failed builds?**  
A: Check console output, build logs, and test reports for errors.

</details>

---

## <a name="production-level-scenarios"></a>📌 Production-Level Scenarios
<details>
<summary>Click to expand Production Q&A</summary>

**⚡Q1: How to handle failed builds in production?**  
A: Analyze console logs, fix errors, rerun pipeline, enable notifications.

**⚡Q2: How to scale Jenkins for large teams?**  
A: Use master-agent architecture, distribute builds across nodes, use cloud agents.

**⚡Q3: How to secure Jenkins?**  
A: Enable authentication, authorization, HTTPS, secrets management, role-based access.

**⚡Q4: How to backup & restore Jenkins?**  
A: Backup `$JENKINS_HOME`, job configs, plugins, credentials; restore on new server.

**Q5: How to improve pipeline performance?**  
A: Parallel stages, caching dependencies, lightweight agents, pipeline optimization.

**Q6: How to audit Jenkins activities?**  
A: Enable audit plugins and monitor logs for user/job actions.

</details>

---

## <a name="best-practices"></a>📌 Best Practices
<details>
<summary>Click to expand Best Practices</summary>

- Use **Declarative Pipelines** for readability.  
- Store Jenkinsfile in version control.  
- Configure **distributed builds** for scalability.  
- Regularly backup Jenkins home and plugins.  
- Enable authentication & role-based access.  
- Limit job retention to save storage.  
- Monitor Jenkins performance and executor usage.  
- Use environment variables & credentials securely.  
- Keep Jenkins and plugins updated.

</details>

---

## <a name="commands--tools-cheat-sheet"></a>📌 Commands / Tools Cheat Sheet
<details>
<summary>Click to expand Cheat Sheet</summary>

- **Jenkins CLI:** `java -jar jenkins-cli.jar -s http://localhost:8080/ command`  
- **List jobs:** `list-jobs`  
- **Build job:** `build JOB_NAME`  
- **Pipeline Groovy snippet example:**  
```groovy
pipeline {
    agent any
    stages { stage('Build') { steps { echo 'Building...' } } }
}
```
- Access parameters: params.PARAM_NAME

- Run shell command: sh 'command'

- Check node info: manage nodes

- Trigger downstream job in pipeline: build job: 'JOB_NAME'
</details> 
