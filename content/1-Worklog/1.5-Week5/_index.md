---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Master AWS's diverse storage solutions and the data lifecycle management process.
* Gain proficiency in applying AI/ML services, data analytics tools, and system integration through hands-on exercises.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Study AWS storage solutions: <br>&emsp; + Object Storage: S3 <br>&emsp; + Block Storage: EBS <br>&emsp; + File Storage: EFS <br>&emsp; + In-memory: ElastiCache <br> - Study data lifecycle management and backup setup | 05/17/2026 | 05/20/2026 | [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/) / [Amazon EBS Documentation](https://docs.aws.amazon.com/ebs/) / [Amazon EFS Documentation](https://docs.aws.amazon.com/efs/) |
| Tue | - Explore the AWS AI/ML ecosystem: <br>&emsp; + Pre-built AI services <br>&emsp; + Machine learning with SageMaker <br>&emsp; + Coding assistance with CodeWhisperer <br> - Study the standard process for deploying an ML model on AWS | 05/20/2026 | 05/22/2026 | [Amazon SageMaker Documentation](https://docs.aws.amazon.com/sagemaker/) / [AWS AI Services](https://aws.amazon.com/ai/services/) |
| Wed | - Explore data analytics services: <br>&emsp; + Serverless querying: Athena <br>&emsp; + Stream processing: Kinesis <br>&emsp; + ETL: Glue <br>&emsp; + Data warehousing: Redshift <br>&emsp; + Visualization: QuickSight | 05/22/2026 | 05/23/2026 | [Amazon Athena Documentation](https://docs.aws.amazon.com/athena/) / [Amazon Kinesis Documentation](https://docs.aws.amazon.com/kinesis/) / [Amazon Redshift Documentation](https://docs.aws.amazon.com/redshift/) |
| Thu | - Study application integration and messaging services: <br>&emsp; + EventBridge: event routing <br>&emsp; + SQS: message queuing <br>&emsp; + SNS: pub/sub notifications <br> - Get an introduction to Connect, SES, and some DevOps tools | 05/23/2026 | 05/24/2026 | [Amazon EventBridge Documentation](https://docs.aws.amazon.com/eventbridge/) / [Amazon SQS Documentation](https://docs.aws.amazon.com/sqs/) / [Amazon SNS Documentation](https://docs.aws.amazon.com/sns/) |
| Fri | - Hands-on integration exercise: <br>&emsp; + Configuring an S3 Lifecycle Policy <br>&emsp; + Building an ML model with SageMaker <br>&emsp; + Building a data pipeline: Kinesis → Glue → Redshift <br>&emsp; + Deploying an event-driven system with EventBridge | 05/24/2026 | 05/24/2026 | [AWS Hands-on Tutorials](https://aws.amazon.com/vi/getting-started/hands-on/) |

### Week 5 Achievements:

\- Clearly distinguished the four AWS storage types and their appropriate use cases: <br>&emsp; \+ Object Storage (S3) – storing static files, backups, building a data lake <br>&emsp; \+ Block Storage (EBS) – volumes attached directly to EC2, suited for databases <br>&emsp; \+ File Storage (EFS) – shared file access across multiple instances <br>&emsp; \+ In-memory (ElastiCache) – caching data to reduce query latency

\- Successfully configured an S3 Lifecycle Policy to automatically transition data between storage classes (Standard → IA → Glacier) and set up periodic backups.

\- Gained an understanding of the AWS AI/ML ecosystem and the standard ML deployment workflow: <br>&emsp; \+ SageMaker – building, training, and deploying ML models <br>&emsp; \+ CodeWhisperer – an AI-powered coding assistant within the IDE <br>&emsp; \+ Workflow: data preparation → training → evaluation → endpoint deployment

\- Successfully practiced building an ML model with SageMaker: <br>&emsp; \+ Preparing a dataset and uploading it to S3 <br>&emsp; \+ Launching a training job and monitoring its progress <br>&emsp; \+ Deploying the model to an endpoint and performing inference

\- Gained a solid understanding of data analytics services and the role each plays: <br>&emsp; \+ Athena – running SQL queries directly on S3 data (serverless, billed by data scanned) <br>&emsp; \+ Kinesis – processing streaming data in real time <br>&emsp; \+ Glue – a serverless ETL service for preparing and transforming data <br>&emsp; \+ Redshift – a large-scale data warehouse for in-depth analytics <br>&emsp; \+ QuickSight – data visualization and dashboard/report building

\- Successfully built a data pipeline connecting Kinesis → Glue → Redshift, and deployed an event-driven system using EventBridge: <br>&emsp; \+ SQS – message queuing that ensures ordered processing without data loss <br>&emsp; \+ SNS – a pub/sub mechanism for broadcasting notifications to multiple subscribers <br>&emsp; \+ EventBridge – automatically routing events between AWS services
