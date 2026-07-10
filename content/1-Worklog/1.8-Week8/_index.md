---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Understand the concepts behind Infrastructure as Code (IaC).
* Learn the basic principles of AWS CDK and Terraform.
* Get an initial introduction to NodeJS fundamentals.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Continue exam review <br> - Explore the core ideas behind IaC: <br>&emsp; + Benefits compared to manual configuration <br>&emsp; + Declarative vs. Imperative approaches | 06/07/2026 | 06/08/2026 | [What Is Infrastructure as Code?](https://aws.amazon.com/what-is/infrastructure-as-code/) |
| Tue | - Get introduced to AWS CDK: <br>&emsp; + Structure: App → Stack → Construct (L1, L2, L3) <br>&emsp; + Supported languages: TypeScript, Python, Java, C# <br>&emsp; + Synthesizing CDK into a CloudFormation template | 06/08/2026 | 06/09/2026 | [AWS CDK Documentation](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Wed | - Study Terraform: <br>&emsp; + File structure: main.tf, variables.tf, outputs.tf <br>&emsp; + Workflow: init → plan → apply → destroy <br>&emsp; + Comparing Terraform with AWS CDK | 06/09/2026 | 06/10/2026 | [Terraform Documentation](https://developer.hashicorp.com/terraform/docs) |
| Thu | - Get introduced to NodeJS: <br>&emsp; + Installing Node.js and npm <br>&emsp; + The Event Loop and the non-blocking I/O model <br>&emsp; + Core modules: fs, path, http, events | 06/10/2026 | 06/12/2026 | [Node.js Documentation](https://nodejs.org/docs/latest/api/) |
| Fri | - Hands-on exercise combining IaC and NodeJS: <br>&emsp; + Deploying AWS infrastructure (S3, Lambda) using CDK or Terraform <br>&emsp; + Writing a NodeJS Lambda function to process S3 events | 06/12/2026 | 06/14/2026 | [AWS Getting Started Resource Center](https://aws.amazon.com/getting-started/) |

### Week 8 Achievements:

\- Gained a solid understanding of the core concepts behind Infrastructure as Code (IaC): <br>&emsp; \+ Benefits over manual configuration: reusability, version control, environment consistency <br>&emsp; \+ Two main approaches: Declarative (Terraform) and Imperative (AWS CDK) <br>&emsp; \+ The IaC lifecycle: write → test → deploy → update → destroy

\- Understood the foundation and structural model of AWS CDK: <br>&emsp; \+ App → Stack → Construct (L1, L2, L3) <br>&emsp; \+ Support for multiple programming languages: TypeScript, Python, Java, C# <br>&emsp; \+ Synthesizing a CDK app into a CloudFormation template

\- Gained a clear understanding of Terraform's syntax and workflow: <br>&emsp; \+ File structure: main.tf, variables.tf, outputs.tf, providers.tf <br>&emsp; \+ Workflow: terraform init → plan → apply → destroy <br>&emsp; \+ Comparison with CDK: Terraform uses its own HCL language, while CDK uses familiar programming languages

\- Successfully set up and got acquainted with the NodeJS environment: <br>&emsp; \+ Installing Node.js and npm, managing packages via package.json <br>&emsp; \+ Understanding the Event Loop and Node.js's non-blocking I/O model <br>&emsp; \+ Working with core modules: fs, path, http, events

\- Completed a hands-on exercise combining IaC and NodeJS: <br>&emsp; \+ Successfully deployed AWS infrastructure (an S3 bucket, a Lambda function) using CDK or Terraform <br>&emsp; \+ Wrote a NodeJS Lambda function to process events triggered by S3
