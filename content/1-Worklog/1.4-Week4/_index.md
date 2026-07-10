---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Research and consolidate database migration approaches on AWS.
* Build a systematic understanding of AWS networking infrastructure, security, and content delivery services.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Define objectives and identify challenges in database migration: <br>&emsp; + Ensuring schema compatibility across different engines <br>&emsp; + Minimizing downtime during the migration process | 05/10/2026 | 05/14/2026 | [AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html) |
| Tue | - Study the AWS migration toolset: <br>&emsp; + DMS, SCT <br>&emsp; + Snow Family, DataSync <br>&emsp; + Real-world application scenarios | 05/14/2026 | 05/15/2026 | [AWS Schema Conversion Tool](https://docs.aws.amazon.com/SchemaConversionTool/latest/userguide/CHAP_Welcome.html) / [AWS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html) |
| Wed | - The four-stage data migration process: <br>&emsp; + Assessment – evaluating source data and risks <br>&emsp; + Preparation – setting up the target environment <br>&emsp; + Execution – performing full load plus CDC <br>&emsp; + Validation & Optimization – verifying results and optimizing | 05/15/2026 | 05/16/2026 | [AWS DMS Best Practices](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_BestPractices.html) |
| Thu | - Study the Amazon VPC network architecture: <br>&emsp; + Subnet, Route Table, Internet/NAT Gateway <br>&emsp; + Security Group and Network ACL <br>&emsp; + PrivateLink, Site-to-Site VPN, Direct Connect | 05/16/2026 | 05/17/2026 | [Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) / [AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/Welcome.html) |
| Fri | - Consolidate knowledge of Route 53 and CloudFront: <br>&emsp; + Route 53: DNS routing with Weighted, Latency-based, Failover policies <br>&emsp; + CloudFront: CDN, Edge Locations, integrated with WAF and Shield | 05/17/2026 | 05/17/2026 | [Amazon Route 53](https://docs.aws.amazon.com/route53/latest/developerguide/Welcome.html) / [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |

### Week 4 Achievements:

\- Identified common challenges in database migration and learned to choose the right strategy to address them: <br>&emsp; \+ Ensuring schema compatibility across different database engines <br>&emsp; \+ Minimizing downtime throughout the migration process <br>&emsp; \+ Preserving performance and data integrity after the migration completes

\- Understood how the AWS Migration toolset operates: <br>&emsp; \+ DMS: creating a replication instance → configuring source/target endpoints → running migration tasks (full load + CDC) <br>&emsp; \+ SCT: automatically analyzing and converting schemas between different engines <br>&emsp; \+ Snow Family: Snowcone (TB scale), Snowball Edge (PB scale), Snowmobile (Exabyte scale) <br>&emsp; \+ DataSync: continuously synchronizing file storage between on-premises systems and AWS

\- Became proficient in the four-stage data migration process: <br>&emsp; \+ Assessment – evaluating the source data and potential risks <br>&emsp; \+ Preparation – setting up the target environment and required tools <br>&emsp; \+ Execution – performing full load combined with Change Data Capture (CDC) <br>&emsp; \+ Validation & Optimization – verifying correctness and optimizing performance

\- Gained a solid understanding of the VPC network architecture and its security layers: <br>&emsp; \+ Subnet (Public/Private), Route Table, Internet Gateway, NAT Gateway <br>&emsp; \+ Security Group (stateful) versus Network ACL (stateless) <br>&emsp; \+ Private connectivity methods: PrivateLink (within AWS), Site-to-Site VPN (over the internet), Direct Connect (dedicated physical link)

\- Distinguished the roles and real-world use cases of Route 53 and CloudFront: <br>&emsp; \+ Route 53: DNS routing with policies such as Simple, Weighted, Latency-based, Failover, Geolocation <br>&emsp; \+ CloudFront: caching content at Edge Locations, integrated with WAF and Shield to protect applications from DDoS attacks
