---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# Hardening Security with Session Policies in Amazon EKS Pod Identity

Amazon EKS Pod Identity is a mechanism that lets Pods securely access AWS services without managing static access keys. Amazon EKS recently added a Session Policies capability, which lets you attach a temporary IAM policy at the moment a Pod assumes an IAM Role. This allows a Pod's effective permissions to be narrowed flexibly while still reusing existing IAM Roles, making permission management in large Kubernetes clusters considerably simpler.

![Session Policies in Amazon EKS Pod Identity](/images/blogs/blog1.jpeg)

## Key Takeaways

* Session Policies take effect exactly when a Pod assumes an IAM Role: the policy is applied during the AssumeRole step to narrow the Pod's access to AWS resources, without requiring a brand-new IAM Role.
* Effective permissions are the intersection of the IAM Role and the Session Policy: a Pod can only perform actions allowed by both the IAM Role and the Session Policy. A Session Policy can only restrict permissions further — it can never grant permissions beyond the underlying Role.
* Simplifies IAM management: a single IAM Role can be shared across many Pods, while Session Policies fine-tune the permission level for each workload, significantly cutting down the number of IAM Roles to maintain.
* Reinforces the least-privilege principle: each Pod's permissions stay tightly scoped to its actual needs, limiting the blast radius if a Pod or application is ever compromised.
* Flexible to deploy: Session Policies are declared through the Pod Identity Association and can be managed via the AWS Management Console, AWS CLI, or AWS SDK, making them easy to fold into deployment pipelines and automation.
* Well suited to large-scale Amazon EKS environments: fewer IAM Roles means simpler administration, less risk of hitting IAM limits, and easier scaling as the number of Pods or applications grows.

This capability is especially valuable in microservices architectures, where many Pods share a single IAM Role but need different scopes of access to AWS resources. For instance, one Pod may only need read access to a specific Amazon S3 bucket, while another needs additional access to Amazon DynamoDB or Amazon SQS. By combining Pod Identity with Session Policies, a system keeps centralized management while still ensuring each Pod holds only the permissions it actually needs to do its job.

[View the post on AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203235167108110/?rdid=fZAE516uaJXkvqmj&share_url=https%3A%2F%2Fwww.facebook.com%2Fshare%2Fp%2F1Bf61McbW7%2F)

---

## References

* [Amazon EKS Pod Identity – AWS Documentation](https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html)
* [Session Policies – AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_session)