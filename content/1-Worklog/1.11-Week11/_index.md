---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Design the core API set for the FlashLearn system.
* Build the database and a content management interface.
* Implement an automated content approval workflow.
* Improve storage resource management using S3 Presigned URLs.
* Finalize the technical documentation and Entity-Relationship Diagram (ERD).

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Design RESTful APIs for Flashcards and Quizzes: <br>&emsp; + POST /flashcards (Create), GET, PUT, DELETE <br>&emsp; + Validating input data (character limits, question format) <br>&emsp; + Integrating JWT authentication via an API Gateway Authorizer | 06/28/2026 | 06/29/2026 | [Building a RESTful API with API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started.html) |
| Tue | - Build the database and admin interface: <br>&emsp; + Creating a flashcards table with a status column (pending/approved/rejected) <br>&emsp; + Creating a quiz_results table <br>&emsp; + Building an admin interface for content management (view, approve, reject) | 06/29/2026 | 06/30/2026 | |
| Wed | - Build the automated content approval workflow: <br>&emsp; + When an admin approves content → Lambda automatically updates the search index <br>&emsp; + EventBridge sends a notification to the content creator | 07/01/2026 | 07/02/2026 | |
| Thu | - Create S3 Presigned URLs for upload/download: <br>&emsp; + Time-limited presigned URLs for uploading directly to S3 <br>&emsp; + CloudFront delivering images/audio via signed URLs <br>&emsp; + Reducing server bandwidth load | 07/02/2026 | 07/03/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Fri | - Finalize technical documentation and the ERD: <br>&emsp; + A complete ERD: Users, Flashcards, Decks, Quiz, QuizResults, Battle, Progress, AuditLogs <br>&emsp; + API documentation covering endpoints, request/response schemas, and error codes | 07/03/2026 | 07/05/2026 | [Entity-Relationship Diagram Design Guide](https://lucid.co/diagram/erd/tutorial) |

### Week 11 Achievements:

\- Designed and finalized the core RESTful API set for the FlashLearn system: <br>&emsp; \+ Flashcard API: POST /flashcards (Create), GET /flashcards/{id}, PUT, DELETE with input validation <br>&emsp; \+ Quiz API: defining question structure, answer format, and character limits <br>&emsp; \+ Integrated JWT authentication via an API Gateway Authorizer

\- Successfully built the database and content management interface: <br>&emsp; \+ Created a flashcards table with a status column (pending/approved/rejected) and a quiz_results table <br>&emsp; \+ Built an admin interface supporting viewing, approving, rejecting, and editing flashcard content <br>&emsp; \+ Scoped admin permissions through a dedicated IAM Role

\- Built an automated content approval workflow: <br>&emsp; \+ When an admin approves content → Lambda is automatically triggered to update the search index <br>&emsp; \+ Sent EventBridge notifications to the content creator whenever the status changes <br>&emsp; \+ Logged the full approval history into an audit_logs table

\- Improved storage resource management using S3 Presigned URLs: <br>&emsp; \+ Created time-limited presigned URLs allowing users to upload files directly to S3, bypassing the server <br>&emsp; \+ CloudFront delivering images/audio from S3 via signed URLs, preventing unauthorized access to resources <br>&emsp; \+ Reduced server bandwidth load, improving upload speed

\- Finalized the system's technical documentation and ERD: <br>&emsp; \+ A complete ERD covering the entities: Users, Flashcards, Decks, Quiz, QuizResults, Battle, Progress, AuditLogs <br>&emsp; \+ Defined the 1-to-many and many-to-many relationships, along with primary and foreign keys for each table <br>&emsp; \+ Detailed API documentation covering endpoints, request/response structures, and error codes
