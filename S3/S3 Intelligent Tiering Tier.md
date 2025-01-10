---
title: S3 Intelligent Tiering Tier
updated: 2024-12-09 02:47:14Z
created: 2024-12-09 02:45:54Z
latitude: 40.76843420
longitude: -74.14542140
altitude: 0.0000
---

Amazon S3 Intelligent-Tiering is a storage class designed to optimize costs by automatically moving data between two access tiers (frequent and infrequent) based on changing access patterns. 

When you upload data to S3 Intelligent-Tiering, it is automatically stored in the Frequent Access tier, which is optimized for data that is accessed frequently. 

If an object hasn’t been accessed for 30 consecutive days, S3 Intelligent-Tiering moves it to the Infrequent Access tier, which is less expensive. 
If an object in the Infrequent Access tier is accessed later, it is automatically moved back to the Frequent Access tier. 
This automatic tiering allows you to optimize storage costs without impacting data retrieval times or requiring operational overhead.