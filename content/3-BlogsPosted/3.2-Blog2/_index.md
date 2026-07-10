---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Event-Driven Architecture on AWS: EventBridge, SNS, and SQS in a Serverless System

Event-Driven Architecture is a system design approach where components communicate through events rather than calling one another directly via REST APIs. On AWS, this pattern can be implemented effectively by combining Amazon API Gateway, AWS Lambda, Amazon EventBridge, Amazon SNS, and Amazon SQS — reducing dependencies between services, improving scalability, and keeping the system stable while handling asynchronous workloads.

![Event-Driven Architecture on AWS](/images/blogs/blog2.jpeg)

## Key Takeaways

* The producer only emits events: once business logic finishes running, AWS Lambda sends an event to Amazon EventBridge instead of calling another service directly, reducing coupling between components.
* Amazon EventBridge handles event routing: it receives, filters, and forwards events based on configured rules, and can also relay events across multiple AWS accounts.
* Amazon SNS implements a publish/subscribe pattern: a single event can be broadcast simultaneously to multiple subscribers — AWS Lambda, Amazon SQS, an HTTP endpoint, or email — without the producer needing any changes.
* Amazon SQS handles asynchronous processing: acting as a queue, SQS buffers events temporarily, absorbs sudden traffic spikes, and supports retries and a Dead Letter Queue (DLQ) to prevent data loss when a consumer fails.
* The architecture scales easily: adding new capabilities — sending emails, audit logging, feeding a data lake, or machine learning — only requires registering a new consumer, without touching existing components.
* Cost-efficient and scalable: relying on serverless services like API Gateway, Lambda, EventBridge, SNS, and SQS lets the system automatically scale with actual traffic and only incur costs when requests are being processed.

This architecture is particularly well suited to microservices systems, asynchronous processing, multi-system integrations, or multi-account AWS environments — anywhere that calls for high scalability, loose coupling between services, and stronger fault tolerance across the whole system.

[View the post on AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203146967116930/?rdid=HY6kGYPyWz6qbEgn&share_url=https%3A%2F%2Fwww.facebook.com%2Fshare%2Fp%2F19BpYphs7p%2F)

---

## References

* [Amazon EventBridge – AWS Documentation](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html)
* [Amazon SNS – AWS Documentation](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)
* [Amazon SQS – AWS Documentation](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)