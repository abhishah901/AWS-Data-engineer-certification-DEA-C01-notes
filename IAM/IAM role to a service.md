---
title: IAM role to a service
updated: 2024-11-09 04:37:35Z
created: 2024-11-09 04:35:27Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

To perform its operations, an AWS service needs to interact with other AWS services on your behalf. This is achieved by using an IAM role that has the necessary permissions. 

When you create an IAM role for AWS Glue, you grant your IAM role permissions that the AWS service can assume when calling other services on your behalf. This includes access to Amazon S3 for any sources, targets, scripts, and temporary directories that you use with AWS services like AWS Glue.

By creating a new IAM service role for a specific AWS service and attaching the necessary policies to this role, you can grant the necessary permissions to that specific sercive without affecting other services or users. 


This approach also aligns with the principle of least privilege, which is a best practice in IAM. This principle encourages you to grant only the permissions required to perform a task.