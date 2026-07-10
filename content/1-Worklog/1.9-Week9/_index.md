---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Begin building FlashLearn – a web application that helps users learn English through flashcards, quizzes, battle mode, and a learning community.
* Set up a modern system architecture on AWS (Singapore region) with a VPC spanning two Availability Zones to ensure high availability.
* Optimize application performance by combining a serverless model with managed services such as Amazon CloudFront, Lambda, and EventBridge.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Kickoff meeting for the FlashLearn project: <br>&emsp; + Finalizing the PostgreSQL database schema design <br>&emsp; + Collecting and standardizing an English vocabulary dataset | 06/14/2026 | 06/15/2026 | |
| Tue | - Build a multi-AZ VPC network architecture: <br>&emsp; + A VPC with 2 public subnets and 2 private subnets <br>&emsp; + Configuring an IAM Role for EC2 following least privilege <br>&emsp; + Setting up layered Security Groups | 06/15/2026 | 06/16/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed | - Configure the ALB and static content delivery: <br>&emsp; + ALB routing traffic based on health checks <br>&emsp; + Uploading static assets to S3 <br>&emsp; + Integrating CloudFront CDN | 06/16/2026 | 06/18/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu | - Team meeting: review UI/UX designs in Figma: <br>&emsp; + Reviewing the flashcard, quiz, and battle screens <br>&emsp; + Refining the user experience flow | 06/18/2026 | 06/19/2026 | |
| Fri | - Build the notification and text-to-speech system: <br>&emsp; + An EventBridge rule triggering Lambda to send study reminders <br>&emsp; + Integrating Amazon Polly to convert text to speech | 06/19/2026 | 06/21/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |

### Week 9 Achievements:

\- Finalized the PostgreSQL database schema design for the FlashLearn system: <br>&emsp; \+ Defined the core tables: Users, Flashcards, Decks, Quiz, Battle, Progress <br>&emsp; \+ Set up foreign key relationships and indexes to optimize query performance <br>&emsp; \+ Collected and standardized the English vocabulary dataset

\- Successfully built a highly available, multi-AZ VPC network architecture on AWS Singapore: <br>&emsp; \+ A VPC with 2 public subnets and 2 private subnets spread across 2 Availability Zones <br>&emsp; \+ Configured an IAM Role for EC2 following the least-privilege principle <br>&emsp; \+ Set up layered Security Groups for each application tier

\- Configured the Application Load Balancer and deployed static content delivery: <br>&emsp; \+ ALB routing traffic to EC2 instances based on health checks <br>&emsp; \+ Created and configured an S3 bucket to store static assets <br>&emsp; \+ Integrated CloudFront CDN to deliver content with low latency worldwide

\- Improved the user experience through a team review session in Figma: <br>&emsp; \+ Reviewed and refined the UI/UX of the flashcard, quiz, and battle screens <br>&emsp; \+ Adjusted the user flow based on team feedback

\- Successfully built an automated notification system and a text-to-speech feature: <br>&emsp; \+ An EventBridge rule triggering Lambda on a schedule to send study reminders <br>&emsp; \+ Integrated Amazon Polly to convert vocabulary text into speech <br>&emsp; \+ Lambda processes the events and stores the results in S3
