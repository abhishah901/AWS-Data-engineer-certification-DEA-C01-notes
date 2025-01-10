---
title: S3 Access Points
updated: 2024-11-13 00:34:11Z
created: 2024-11-13 00:32:55Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon S3 Access Points are a feature of Amazon S3 that simplifies managing data access for shared datasets. 

With Access Points, you can create multiple access points for a single S3 bucket, with each access point having a unique hostname and access policy tailored for a specific use case or application.

Each access point can be configured with a custom access policy granting only the necessary permissions for its intended use.

Access points allow separating access control for different applications rather than managing everything through a single bucket policy.

Network controls can be applied to access points to restrict access to only requests from a specific VPC.

Access points can be used to grant cross-account access while still retaining control over the bucket and data through the bucket policy.

Aliases are automatically generated for each access point, making them interchangeable with bucket names in AWS APIs and CLI.

Common S3 operations can be performed by replacing the bucket name with the access point ARN or alias.