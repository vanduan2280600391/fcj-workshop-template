---
title: "Week 12 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Finalize community interaction features for the FlashLearn system.
* Build the scoring and user ranking logic.
* Implement a nested comment system.
* Log user activity into the database.
* Finalize technical documentation and hand off the project.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Team meeting to design community interaction APIs: <br>&emsp; + Flashcard voting API (upvote/downvote) <br>&emsp; + Quiz ranking API based on completion time and accuracy rate | 07/05/2026 | 07/06/2026 | |
| Tue | - Build the scoring and ranking logic: <br>&emsp; + Awarding points for: upvotes, completing quizzes, having a flashcard approved <br>&emsp; + Deducting points for: downvotes, rule violations <br>&emsp; + A leaderboard segmented by week/month/all-time | 07/06/2026 | 07/07/2026 | |
| Wed | - Design the nested comment system: <br>&emsp; + A data structure supporting nested replies (parent_id) <br>&emsp; + Automatically updating the comment_count counter <br>&emsp; + Moderating comment content through Lambda | 07/07/2026 | 07/08/2026 | |
| Thu | - Add and finalize remaining features: <br>&emsp; + A "Favorite" feature for flashcards/quizzes <br>&emsp; + Logging user activity into a user_activities table <br>&emsp; + Activity data feeding into the smart study recommendation feature | 07/08/2026 | 07/09/2026 | |
| Fri | - Team meeting to finalize documentation and hand off the project: <br>&emsp; + API documentation following the Swagger/OpenAPI spec for all endpoints <br>&emsp; + A complete system-wide ERD (10+ tables) <br>&emsp; + A handover package: architecture, deployment guide, account information | 07/09/2026 | 07/10/2026 | |

### Week 12 Achievements:

\- Finalized the community interaction APIs for FlashLearn: <br>&emsp; \+ Flashcard voting API: POST /flashcards/{id}/vote (upvote/downvote) <br>&emsp; \+ Quiz ranking API: scoring based on completion time and correct-answer rate <br>&emsp; \+ Leaderboard updated in real time via DynamoDB

\- Successfully built the scoring and ranking logic: <br>&emsp; \+ Awarding points when users upvote, complete a quiz, or get a flashcard approved <br>&emsp; \+ Deducting points for downvotes or rule violations <br>&emsp; \+ A leaderboard segmented by week/month/all-time

\- Fully built the nested comment system: <br>&emsp; \+ A data structure supporting comments and nested replies (parent_id) <br>&emsp; \+ Automatically updating the comment_count for each flashcard/quiz <br>&emsp; \+ Moderating comment content via Lambda before it goes live

\- Finalized the Favorite feature and user activity logging: <br>&emsp; \+ Users can save favorite flashcards/quizzes to a personal space <br>&emsp; \+ A user_activities table records every action: viewing, studying, voting, commenting <br>&emsp; \+ This activity data underpins the smart study recommendation feature

\- Successfully finalized the technical documentation and handed off the project: <br>&emsp; \+ Complete API documentation following the Swagger/OpenAPI spec for all endpoints <br>&emsp; \+ A complete system-wide ERD with 10+ tables and their relationships <br>&emsp; \+ A handover package including: system architecture, deployment guide, account information, and access permissions
