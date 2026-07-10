---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Master the Amazon EC2 architecture, load distribution mechanisms, and automatic resource-scaling strategies.
* Understand modern data storage models along with database migration approaches for AWS.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Dive into the EC2 architecture: <br>&emsp; + Grouping instances by workload characteristics <br>&emsp; + Related components: AMI, VPC, Security Group, EBS <br>&emsp; + Access methods: SSH, EC2 Instance Connect, Session Manager | 05/03/2026 | 05/06/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| Tue | - Study load balancing (ELB) and automatic resource scaling (Auto Scaling): <br>&emsp; + Application Load Balancer (ALB) <br>&emsp; + Auto Scaling Group and Scaling Policies | 05/06/2026 | 05/08/2026 | [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html) / [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) |
| Wed | - Explore Container and Serverless solutions on AWS: <br>&emsp; + Containers: ECS, EKS <br>&emsp; + Serverless: AWS Lambda, Fargate | 05/08/2026 | 05/09/2026 | [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) / [Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html) / [AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Thu | - Study the database families available on AWS: <br>&emsp; + SQL: RDS (MySQL, PostgreSQL), Aurora <br>&emsp; + NoSQL: DynamoDB <br>&emsp; + In-memory: MemoryDB | 05/09/2026 | 05/10/2026 | [Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) / [Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) |
| Fri | - Research data migration strategies using the 6R model: <br>&emsp; + Supporting tools: DMS, SCT, Snow Family, DataSync <br>&emsp; + How to choose the right solution for each scenario | 05/10/2026 | 05/10/2026 | [AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html) / [AWS Snow Family](https://aws.amazon.com/snow/) |

### Week 3 Achievements:

\- Classified the EC2 architecture in detail by workload type and gained a solid grasp of the configuration components: <br>&emsp; \+ AMI, VPC, Security Group, EBS <br>&emsp; \+ Remote connection methods: SSH Key Pair, EC2 Instance Connect, Session Manager

\- Understood the principles of load distribution and automatic resource scaling: <br>&emsp; \+ Application Load Balancer (ALB) – routes based on path/host <br>&emsp; \+ Scaling Policies: Target Tracking, Step Scaling, Scheduled Scaling <br>&emsp; \+ Combining ELB with an Auto Scaling Group to ensure high availability

\- Clearly distinguished the Container and Serverless models on AWS: <br>&emsp; \+ ECS (EC2 launch type) versus EKS (Kubernetes platform) <br>&emsp; \+ Fargate – serverless containers with no server management required <br>&emsp; \+ AWS Lambda – event-driven, billed based on invocation count and execution time

\- Learned to classify and choose the right database service based on requirements: <br>&emsp; \+ SQL: RDS (MySQL, PostgreSQL), Aurora (high performance) <br>&emsp; \+ NoSQL: DynamoDB (key-value/document, low latency) <br>&emsp; \+ In-memory: MemoryDB (Redis-compatible, durable)

\- Grasped the 6R data migration strategy model and the role of each tool: <br>&emsp; \+ AWS DMS – online database migration <br>&emsp; \+ AWS SCT – automatic schema conversion between different engines <br>&emsp; \+ Snow Family – large-scale offline data migration (TB to PB) <br>&emsp; \+ DataSync – continuous, automated file storage synchronization
