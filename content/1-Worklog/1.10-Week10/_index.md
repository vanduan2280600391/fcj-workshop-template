---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Improve FlashLearn's performance through caching, automated image processing, and comprehensive API testing.
* Build a smart study recommendation feature based on user history.
* Set up a monitoring system to track application performance on AWS.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Team meeting to plan performance improvements: <br>&emsp; + Improving RDS PostgreSQL query performance (adding indexes) <br>&emsp; + Configuring CloudFront caching with appropriate TTLs | 06/21/2026 | 06/22/2026 | |
| Tue | - Hands-on practice optimizing image processing with Lambda: <br>&emsp; + Lambda auto-triggered when images are uploaded to S3 <br>&emsp; + Resizing images to standard sizes (thumbnail, medium, large) <br>&emsp; + Compressing images to WebP format to reduce storage size | 06/22/2026 | 06/23/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed | - Comprehensive API testing with Postman: <br>&emsp; + Testing CRUD operations through API Gateway <br>&emsp; + Verifying CORS configuration for the frontend <br>&emsp; + Testing IAM authorization | 06/23/2026 | 06/24/2026 | |
| Thu | - Team meeting to build the smart study recommendation feature: <br>&emsp; + An algorithm based on study history (frequency, correct/incorrect ratio) <br>&emsp; + Designing the flow: Lambda reads the Progress table → computes → returns results | 06/24/2026 | 06/26/2026 | |
| Fri | - Set up a monitoring system on AWS: <br>&emsp; + A CloudWatch Dashboard tracking EC2 CPU, Memory, and Network (ARM64) <br>&emsp; + CloudWatch Alarms triggering when RDS CPU exceeds 80% <br>&emsp; + AWS X-Ray tracing internal API calls to identify bottlenecks | 06/26/2026 | 06/28/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |

### Week 10 Achievements:

\- Successfully improved RDS PostgreSQL query performance and CloudFront caching: <br>&emsp; \+ Added indexes on frequently queried columns (user_id, deck_id, created_at) <br>&emsp; \+ Configured a CloudFront Cache Policy with appropriate TTLs for each type of static content <br>&emsp; \+ Reduced the average response time for complex queries

\- Successfully built an automated image-processing pipeline with Lambda: <br>&emsp; \+ Lambda automatically triggered whenever an image is uploaded to S3 <br>&emsp; \+ Resizing images to standard sizes (thumbnail, medium, large) and compressing them to WebP <br>&emsp; \+ Storing image versions under separate S3 prefixes, significantly reducing storage usage

\- Completed comprehensive API testing with Postman: <br>&emsp; \+ Fully tested CRUD operations (GET, POST, PUT, DELETE) through API Gateway <br>&emsp; \+ Verified that CORS configuration worked correctly for the frontend <br>&emsp; \+ Tested IAM authorization to ensure only permitted roles could call the API

\- Built and refined the smart study recommendation feature: <br>&emsp; \+ Developed a recommendation algorithm based on study history (review frequency, correct/incorrect ratio, study time) <br>&emsp; \+ Designed the data flow: Lambda reads the Progress table → performs calculations → returns a prioritized word list

\- Set up comprehensive monitoring on AWS: <br>&emsp; \+ A CloudWatch Dashboard tracking EC2 CPU, Memory, and Network (ARM64) <br>&emsp; \+ CloudWatch Alarms alerting when RDS CPU exceeds 80% or connections exceed a threshold <br>&emsp; \+ AWS X-Ray tracing internal API calls to identify bottlenecks in the processing flow
