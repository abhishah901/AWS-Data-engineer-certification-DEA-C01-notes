---
title: Overview
updated: 2024-11-13 05:15:01Z
created: 2024-11-13 05:14:53Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

AWS KMS allows you to enable automatic key rotation for your customer-managed keys, which automatically generates new cryptographic material for your key every year. 

To rotate a key manually, you would create new cryptographic material and associate it with the key yourself. 

This process involves generating a new version of the key while retaining the ability to access the previous versions, including all primary and replica key versions. 

Manual rotation provides direct control over the timing and process of the rotation, aligning with specific security policies that require such control. 

Additionally, this process can be automated using services such as AWS Lambda and Amazon EventBridge, allowing for custom rotation schedules and procedures that meet specific organizational requirements.