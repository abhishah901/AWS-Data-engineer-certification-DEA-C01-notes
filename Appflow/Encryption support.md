---
title: Encryption support
updated: 2024-12-04 23:52:44Z
created: 2024-12-04 23:52:38Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon AppFlow provides both AWS managed and customer managed keys for encrypting connection data and data stored in Amazon S3 when it is a destination. We recommend that you use a customer managed keys, as it puts you in full control over your encrypted data. When you choose a customer managed keys, Amazon AppFlow attaches a resource policy to the KMS key that grants it access to the KMS key.