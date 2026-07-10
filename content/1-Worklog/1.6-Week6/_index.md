---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Dive deeper into automated security tools to improve monitoring capabilities and response to potential risks.
* Strengthen skills in configuring fine-grained IAM permissions, distinguishing between roles and users to properly apply the principle of least privilege in a cloud environment.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Study the AWS security foundations: <br>&emsp; + The Shared Responsibility Model <br>&emsp; + The importance of protecting data in the cloud | 05/24/2026 | 05/25/2026 | [AWS Well-Architected: Shared Responsibility Model](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/shared-responsibility.html) |
| Tue | - Study compliance governance on AWS: <br>&emsp; + International standards and regulations <br>&emsp; + The 5 core functions: Identify, Protect, Detect, Respond, Recover | 05/25/2026 | 05/27/2026 | [AWS Compliance Programs](https://aws.amazon.com/vi/compliance/) |
| Wed | - Evaluate automated security tools: <br>&emsp; + Security Hub <br>&emsp; + Trusted Advisor <br>&emsp; + Amazon GuardDuty | 05/27/2026 | 05/28/2026 | [Amazon GuardDuty](https://aws.amazon.com/vi/guardduty/) |
| Thu | - Identity and Access Management (IAM): <br>&emsp; + The Least Privilege principle <br>&emsp; + Securing the root account and MFA <br>&emsp; + Managing secrets with Secrets Manager | 05/28/2026 | 05/29/2026 | [AWS IAM Documentation](https://docs.amazonaws.cn/iam/) |
| Fri | - IAM deep dive: <br>&emsp; + Distinguishing IAM Users from IAM Roles <br>&emsp; + Setting up access policies <br>&emsp; + Attaching permissions to EC2/Lambda resources | 05/29/2026 | 05/31/2026 | [AWS Builder: IAM Identity and Access Management](https://builder.aws.com/content/3C3mJwaTB5NWzcBfEugE7AUx59H/iam-identity-and-access-management) |

### Week 6 Achievements:

\- Gained a solid grasp of the AWS Shared Responsibility Model: <br>&emsp; \+ AWS is responsible for securing the physical infrastructure, hypervisor, and underlying platform services <br>&emsp; \+ Customers are responsible for securing their data, applications, OS configuration, and access permissions

\- Understood the compliance governance framework and its 5 core functions: <br>&emsp; \+ Identify – recognizing assets and potential risks <br>&emsp; \+ Protect – implementing control measures <br>&emsp; \+ Detect – continuously monitoring for anomalies <br>&emsp; \+ Respond – handling incidents promptly <br>&emsp; \+ Recover – restoring systems after an incident

\- Evaluated and became proficient with automated security tools: <br>&emsp; \+ Security Hub – aggregating and prioritizing security findings from multiple services <br>&emsp; \+ Trusted Advisor – reviewing configurations against best practices (security, cost, performance) <br>&emsp; \+ GuardDuty – intelligent threat detection powered by ML, analyzing CloudTrail, VPC Flow Logs, and DNS logs

\- Configured IAM according to the least-privilege principle: <br>&emsp; \+ Securing the root account: enabling MFA and avoiding root use for everyday tasks <br>&emsp; \+ Creating IAM Users with permissions scoped to specific job functions <br>&emsp; \+ Managing secrets using AWS Secrets Manager and Parameter Store

\- Clearly distinguished IAM Users from IAM Roles and set up detailed access policies: <br>&emsp; \+ IAM User – a fixed identity for a person or application <br>&emsp; \+ IAM Role – a temporary identity attached to EC2/Lambda or other AWS services to access resources <br>&emsp; \+ Inline Policy versus Managed Policy – differences in scope and reusability
