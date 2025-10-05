# ![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-blue?style=for-the-badge)
##  GitHub Actions Interview Questions & Answers

---

##  Basics
<details>
<summary>Click to expand</summary>

**Q1:** What is GitHub Actions and why is it used?  
**A1:** GitHub Actions is a CI/CD and automation tool built into GitHub that allows developers to automate workflows for building, testing, and deploying applications whenever code changes. It removes the need for separate CI/CD tools.  

**Q2:** What are the main components of GitHub Actions?  
**A2:** Workflow, Job, Step, Action, Runner.  

**Q3:** What is a workflow file, and where is it located?  
**A3:** A YAML file defining the automation process. It is stored inside `.github/workflows/`.  

**Q4:** What is the difference between a job and a step?  
**A4:** A job is a set of steps run on a runner. A step is an individual task within a job.  

**Q5:** What is a runner?  
**A5:** A virtual machine (GitHub-hosted or self-hosted) where jobs are executed.  

**Q6:** What is a self-hosted runner?  
**A6:** A runner installed and managed by the user on their own machine, providing control over environment, OS, and resources.  

**Q7:** How do you manually trigger a workflow?  
**A7:** Use `workflow_dispatch` in the workflow YAML file and trigger it via the GitHub UI.  

**Q8:** How do you define a simple CI workflow?  
**A8:**  
```yaml
name: CI Pipeline
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Build
        run: echo "Build step"
```
</details>

## Triggers & Events
<details> <summary>Click to expand</summary>

**Q1:** What are triggers in GitHub Actions?  
**A1:** Events that initiate workflows, defined by the on: keyword in YAML.

**Q2:** Difference between push and pull_request?  
A2: push triggers workflows when code is pushed; pull_request triggers on PR creation or update.

**Q3:** How do you schedule workflows?  
**A3:** Using schedule with a cron expression:

```
on:
  schedule:
    - cron: "0 0 * * *"
```

**Q4:** What is workflow_dispatch?  
**A4:** A trigger to manually run workflows via GitHub UI or API.

**Q5:** How do you trigger workflows only on specific branches?  
**A5:**
``` 
on:
  push:
    branches:
      - main
```

**Q6:** How can you trigger a workflow from another workflow?  
**A6:** Using the workflow_run event or GitHub API.  

</details>

## YAML & Configuration
<details> <summary>Click to expand</summary>

**Q1:** What does runs-on mean?  
**A1:** Specifies the OS runner (e.g., ubuntu-latest).

**Q2:** Difference between run and uses?  
**A2:** run executes shell commands, uses runs prebuilt actions.

**Q3:** How do you pass parameters to an action?  
**A3:** Using the with: keyword in YAML.

**Q4:** How do you conditionally run steps?  
**A4:** Using if: expressions. Example:  

```
if: github.ref == 'refs/heads/main'
```
**Q5:** What is needs: used for?  
**A5:** Specifies job dependencies so jobs run sequentially.  

</details>

## Environment Variables & Secrets
<details> <summary>Click to expand</summary>

**Q1:** How do you define environment variables?  
**A1:**
```
env:
  ENV_VAR: value
```
**Q2:** How to use GitHub Secrets?  
**A2:** Store in repo settings and access via:  

```
${{ secrets.SECRET_NAME }}
```

**Q3:** Difference between env: and secrets:?  
**A3:** env: stores environment variables; secrets: stores encrypted credentials.

**Q4:** How do you mask secrets in logs?  
**A4:** GitHub automatically masks secrets in logs.

</details>

## Docker & CI/CD
<details> <summary>Click to expand</summary>

**Q1:** How do you build Docker images in GitHub Actions?  
**A1:**

```
- run: docker build -t myapp:latest .
```
**Q2:** How do you push Docker images to DockerHub?  
**A2:** Authenticate using secrets and run:
```
- run: docker push myapp:latest
```
**Q3:** How to store Docker credentials?  
**A3:** Use GitHub Secrets (DOCKER_USERNAME, DOCKER_PASSWORD).

**Q4:** How do you tag Docker images?  
**A4:** Use semantic versioning or commit SHA:
```
docker tag myapp:latest myapp:v1.0.0
```
</details>

## Production-Level Questions
<details> <summary>Click to expand</summary>

**Q1:** How do you handle secrets across multiple environments?  
**A1:** Use environment-specific secrets in GitHub environments.

**Q2:** How do you optimize long-running workflows?  
**A2:** Use caching (actions/cache@v3), matrix builds, and selective triggers.

**Q3:** How do you trigger dependent workflows?  
**A3:** Using workflow_run events or reusable workflows.

**Q4:** How do you rollback deployments?  
**A4:** Keep previous Docker images and redeploy them or use Git tags for rollback.

**Q5:** How do you manage concurrent jobs?  
**A5:** Use concurrency in YAML:
```
concurrency:
  group: deploy-${{ github.ref }}
  cancel-in-progress: true
```

**Q6:** How do you handle failed workflow runs?  
**A6:** Use notifications, logs, and optionally rerun failed jobs or roll back changes.

**Q7:** How do you integrate GitHub Actions with Kubernetes?  
A7: Use kubectl commands in a workflow with kubeconfig stored in secrets.

**Q8:** How do you version workflows across multiple repositories?  
**A8:** Use reusable workflows stored in a shared repo and call them using uses:.

**Q9:** How do you secure workflows in production?  
A9: Use branch protection rules, required reviews, and environment approvals.

**Q10:** How do you monitor workflow performance in production?  
**A10:** Use GitHub Actions logs, build time tracking, and third-party integrations like Datadog or Prometheus.

</details>

## Cheat Codes & Tips
<details> <summary>Click to expand</summary>

- Re-run a workflow: Click “Re-run jobs” in GitHub Actions UI.

- Debug workflows: Add ACTIONS_STEP_DEBUG=true in secrets.

- Manual trigger: Use workflow_dispatch.

- Skip workflow: Add [skip ci] in commit message.

- Conditional jobs:
```
if: github.ref == 'refs/heads/main'
```
- Cache dependencies: Use actions/cache@v3.

- Upload artifacts: Use actions/upload-artifact@v3.

- Matrix builds: Use strategy.matrix to run jobs in parallel with different configurations.

</details>



