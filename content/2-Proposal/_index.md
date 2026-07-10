---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# FlashLearn – AWS Cloud Infrastructure Proposal

### 1. Project Overview

FlashLearn is a web application that helps users learn English interactively through flashcards, quizzes, and a community space. Rather than following a traditional monolithic deployment model, this project focuses on building a modern cloud infrastructure on Amazon Web Services (AWS), in the Asia Pacific (Singapore) region. The architecture is designed to closely follow enterprise-grade standards for distribution, multi-layered security, and a high degree of automation.

---

### 2. Objectives

High availability: keep the system running 24/7 by spreading the infrastructure across a Multi-AZ setup covering 2 Availability Zones.

Deep, layered security: block threats right at the network edge with AWS WAF, while fully isolating both the compute layer (EC2) and the data layer (RDS) inside private subnets.

Performance optimization: deliver static content at high speed through a global CDN, and offload the server by handling background tasks separately.

Extending the core feature set: integrating AI to support accurate English pronunciation.

---

### 3. Problem Statement

Many e-learning systems still store media files directly on the server and place that server in a public network zone, creating significant security risk (vulnerable to DDoS attacks, data leaks) as well as bandwidth bottlenecks when many learners access the system at once.

The proposed solution puts S3 and CloudFront at the front line to handle static content, while all business logic (EC2) and data (RDS) stay hidden inside a private network layer. Every outbound connection from the backend must go through a NAT Gateway, and inbound traffic is safely distributed through an Application Load Balancer.

---

### 4. Solution Architecture

The entire system is designed inside a single VPC (10.0.0.0/16) spanning 2 Availability Zones to ensure fault tolerance.

![FlashLearn AWS architecture diagram](/images/2-Proposal/flashlearn_architecture.png)

Component details and processing flow:

Edge layer – security & routing: every user request first passes through Amazon Route 53 (DNS management) combined with AWS WAF, which filters out malicious traffic before it reaches deeper into the system.

Content delivery layer: Amazon CloudFront acts as the CDN, fetching and caching static content from Amazon S3 (flashcard images, the /wwwroot folder), so content reaches users as fast as possible.

Public networking & load balancing layer: two public subnets (10.0.1.0/24 and 10.0.2.0/24) host the Application Load Balancer, which receives dynamic API traffic from the Internet Gateway, along with the NAT Gateways that let internal servers reach the internet for updates.

Business logic & data layer (private subnets): EC2 instances (t4g.micro, ARM64 architecture) handle backend logic and sit entirely inside 2 private subnets (10.0.3.0/24 and 10.0.4.0/24), accepting traffic only from the ALB. The database runs on Amazon RDS PostgreSQL with synchronous replication across 2 Availability Zones, ensuring no data loss if one data center goes down.

Automation & AI integration layer: EC2 makes internal API calls to Amazon Polly to provide text-to-speech functionality. Amazon EventBridge is configured as a cron scheduler that automatically triggers AWS Lambda to run background jobs, and Lambda sends periodic notification emails (e.g., deadline reminders) via Amazon SES.

---

### 5. Implementation Timeline

Week 1 – Network foundation & domain resolution: build the VPC, split it into public/private subnets, and set up Route 53, WAF, and the Internet Gateway.

Week 2 – Compute & load balancing: launch ARM64 EC2 instances inside the private subnets, set up the ALB in the public subnets to route traffic to EC2, and configure the NAT Gateways.

Week 3 – Data & storage: provision a Multi-AZ RDS PostgreSQL instance, create the S3 bucket, and configure CloudFront with OAC for static content delivery.

Week 4 – Serverless & service integration: build the EventBridge → Lambda → SES flow for automated emails, and integrate the Amazon Polly SDK into the EC2 backend code.

Week 5 – Testing, optimization & handover: load-test through the ALB, test the WAF's blocking rules, finalize the system, and produce the infrastructure architecture report.

---

### 6. Budget Estimate

The system is deployed in the Singapore region (ap-southeast-1) on an On-Demand basis. Because this is an enterprise-grade, multi-layer, multi-AZ architecture, costs run higher than a simple single-tier setup:

NAT Gateway (x2): ~$65.70/month (the most expensive component, but required for private EC2 instances to reach the internet).

Application Load Balancer: ~$16.42/month.

Amazon RDS PostgreSQL (Multi-AZ): ~$46.40/month.

Amazon EC2 (t4g.micro x2): ~$12.26/month.

S3, CloudFront, Route 53, WAF: ~$10.00/month (depending on actual traffic).

Polly, Lambda, EventBridge, SES: ~$2.00/month (very low cost thanks to serverless pay-as-you-go pricing).

Estimated total budget: ~$152.78/month.

---

### 7. Risk Assessment

NAT Gateway cost overrun (high impact): NAT Gateway bills by the hour and by data processed. Mitigation: during Dev/Test, use just a single NAT Gateway or temporarily move EC2 into a public subnet to save cost, and only provision both NAT Gateways once moving to acceptance testing or production.

Lost connectivity between the ALB and EC2 (medium impact): a misconfigured security group can block the ALB from forwarding traffic into the private subnet. Mitigation: carefully verify that the EC2 security group only accepts inbound traffic from the ALB's security group, never opening it up to 0.0.0.0/0.

Static/dynamic routing errors in CloudFront (medium impact): CloudFront may mistakenly cache dynamic API requests. Mitigation: configure CloudFront behaviors explicitly so that every /api/* path bypasses the cache and goes straight to the ALB, while only /wwwroot/* paths or media files are served from S3.
