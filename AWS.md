# AWS Interview Preparation

![AWS](https://img.shields.io/badge/AWS-Amazon-orange) ![Interview](https://img.shields.io/badge/Interview-Prep-blue) ![Production Ready](https://img.shields.io/badge/Production-Ready-green)

---

## Table of Contents

<details>
<summary>1. Basics</summary>

- ⚡ **What is AWS?**  
  Cloud computing platform providing on-demand compute, storage, and other services.

- **What are the different cloud service models?**  
  IaaS, PaaS, SaaS.

- **What are the deployment models?**  
  Public, Private, Hybrid, Multi-cloud.

- **Explain regions and availability zones (AZs).**  
  Region = geographical area; AZ = isolated datacenter within a region.

- **What is AWS Free Tier?**  
  Limited free access to services for 12 months or always free options.

</details>

<details>
<summary>2. EC2 (Elastic Compute Cloud)</summary>

- ⚡ **What is EC2?**  
  Virtual servers in the cloud with scalable compute capacity.

- **EC2 Instance Types?**  
  General Purpose, Compute Optimized, Memory Optimized, Storage Optimized, Accelerated Computing.

- **Difference between Spot, On-Demand, and Reserved Instances?**  
  Spot = cheaper but interruptible, On-Demand = pay per hour, Reserved = long-term discount.

- **What is Elastic IP?**  
  Static public IP for EC2, can be reassigned.

- **Security groups vs NACLs?**  
  Security Groups = instance-level firewall, NACL = subnet-level firewall.

</details>

<details>
<summary>3. S3 (Simple Storage Service)</summary>

- ⚡ **What is S3?**  
  Object storage service, highly durable and scalable.

- **S3 Storage Classes?**  
  Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier, Glacier Deep Archive.

- **S3 Bucket policies vs IAM policies?**  
  Bucket policies = resource-based, IAM policies = user/role-based.

- **Enable versioning in S3 – why?**  
  Protects against accidental deletes/overwrites.

- **S3 Event Notifications?**  
  Trigger Lambda, SNS, or SQS on object events.

</details>

<details>
<summary>4. VPC (Virtual Private Cloud)</summary>

- ⚡ **What is a VPC?**  
  Isolated virtual network in AWS for deploying resources.

- **Public vs Private Subnet?**  
  Public = internet-accessible, Private = no direct internet access.

- **What is an Internet Gateway (IGW)?**  
  Enables internet access for VPC resources.

- **What is a NAT Gateway?**  
  Allows private instances to access internet outbound.

- **VPC Peering?**  
  Connects two VPCs privately.

</details>

<details>
<summary>5. IAM & Security</summary>

- ⚡ **What is IAM?**  
  Manage users, roles, permissions securely.

- **Roles vs Users vs Groups?**  
  Users = individual accounts, Groups = user collections, Roles = temporary access.

- **What is a Policy?**  
  JSON document defining allowed/denied actions.

- **MFA – Why important?**  
  Adds extra layer of security beyond username/password.

- **Key Management Service (KMS)?**  
  Manage encryption keys securely.

</details>

<details>
<summary>6. Lambda & Serverless</summary>

- ⚡ **What is AWS Lambda?**  
  Serverless compute; run code without provisioning servers.

- **Trigger types for Lambda?**  
  S3 events, DynamoDB streams, API Gateway, CloudWatch events.

- **Lambda vs EC2?**  
  Lambda = event-driven, pay per execution; EC2 = always-on servers.

- **Lambda cold start?**  
  Delay when function invoked first time or after idle.

</details>

<details>
<summary>7. RDS & Databases</summary>

- ⚡ **What is RDS?**  
  Managed relational database service.

- **Supported engines?**  
  MySQL, PostgreSQL, Oracle, SQL Server, MariaDB, Aurora.

- **Multi-AZ vs Read Replica?**  
  Multi-AZ = HA/failover, Read Replica = horizontal scaling.

- **DynamoDB vs RDS?**  
  DynamoDB = NoSQL, key-value, serverless; RDS = SQL relational.

</details>

<details>
<summary>8. CloudFormation & Infrastructure as Code</summary>

- ⚡ **What is CloudFormation?**  
  AWS IaC service to provision resources via templates.

- **Stack vs Template?**  
  Template = blueprint, Stack = deployed resources from template.

- **Benefits of IaC?**  
  Versioning, repeatability, automation.

</details>

<details>
<summary>9. Auto Scaling & Load Balancing</summary>

- ⚡ **What is Auto Scaling?**  
  Automatically adjusts EC2 capacity based on demand.

- **Types of Load Balancers?**  
  ALB, NLB, CLB.

- **Health checks?**  
  Monitor instance status; replace unhealthy instances.

</details>

<details>
<summary>10. CloudWatch & Monitoring</summary>

- ⚡ **What is CloudWatch?**  
  Monitor AWS resources and applications.

- **CloudWatch metrics vs logs?**  
  Metrics = numeric data, Logs = text-based logs.

- **Alarms?**  
  Trigger actions when metrics breach thresholds.

</details>

<details>
<summary>11. SQS & SNS</summary>

- ⚡ **SQS vs SNS?**  
  SQS = message queue (pull), SNS = notification (push).

- **SQS Types?**  
  Standard = high throughput, FIFO = ordered messages.

- **SNS Fan-out?**  
  Send one message to multiple endpoints/subscriptions.

</details>

<details>
<summary>12. Route 53</summary>

- ⚡ **What is Route 53?**  
  DNS service, routes traffic to AWS resources.

- **Routing policies?**  
  Simple, Weighted, Latency, Failover, Geolocation.

- **Health checks in Route 53?**  
  Monitor endpoints; route traffic away if unhealthy.

</details>

<details>
<summary>13. Cost Optimization</summary>

- ⚡ **How to reduce AWS costs?**  
  Right-sizing, Reserved/Spot instances, S3 lifecycle policies, consolidate resources.

- **Use of Trusted Advisor?**  
  Provides cost-saving and security recommendations.

</details>

<details>
<summary>14. CI/CD with CodePipeline/CodeBuild</summary>

- ⚡ **What is CodePipeline?**  
  Continuous integration/delivery service.

- **CodeBuild vs CodeDeploy?**  
  Build = compile/test code; Deploy = deploy to EC2, Lambda, ECS.

- **Integration with GitHub?**  
  Trigger pipeline on commits/push events.

</details>

<details>
<summary>15. Production-Level Scenarios</summary>

- ⚡ **How to handle high traffic spikes?**  
  Use Auto Scaling + Load Balancers + CloudFront caching.

- ⚡ **Disaster Recovery strategies?**  
  Backup snapshots, multi-region replication, cross-AZ deployment.

- ⚡ **Mitigating downtime during deployment?**  
  Blue/Green or Canary deployment using CodeDeploy/ALB.

- ⚡ **Security breach response?**  
  Rotate keys, revoke compromised roles, enable CloudTrail alerts.

- ⚡ **Cost overruns prevention?**  
  Use budgets, alerts, and auto-scaling to control spend.

</details>

<details>
<summary>16. Best Practices</summary>

- Encrypt data at rest and in transit.  
- Enable CloudTrail for auditing.  
- Use Multi-AZ deployments for production.  
- Implement proper IAM least privilege policies.  
- Use Auto Scaling, Load Balancers, and caching for high availability.  
- Implement backups, snapshots, and DR strategy.  
- Monitor and alert with CloudWatch and Trusted Advisor.  

</details>

<details>
<summary>17. Commands / Tools Cheat Sheet</summary>

- **AWS CLI Basics**  
```bash
  aws s3 ls
  aws ec2 describe-instances
  aws iam list-users
  aws lambda invoke --function-name MyFunction output.txt
```
- CloudFormation
```
  aws cloudformation deploy --template-file template.yml --stack-name my-stack
  aws cloudformation delete-stack --stack-name my-stack
```
- Terraform Basics
```
terraform init
terraform plan
terraform apply
terraform destroy
```
- S3 Management
```
 aws s3 cp file.txt s3://my-bucket/
 aws s3 sync ./localdir s3://my-bucket/
```
- EC2 Management
```
aws ec2 start-instances --instance-ids i-1234567890abcdef0
aws ec2 stop-instances --instance-ids i-1234567890abcdef0
```
</details>


  
