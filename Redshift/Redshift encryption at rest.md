---
title: Redshift encryption at rest
updated: 2024-11-13 05:08:16Z
created: 2024-11-13 05:03:27Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon Redshift supports encryption at rest and in transit. For encryption at rest, it uses keys managed through AWS Key Management Service (KMS). 

When you create a table in Redshift, you can choose to encrypt your data at rest by selecting an encryption key. If you don’t choose a key, Redshift takes the default key for the account.