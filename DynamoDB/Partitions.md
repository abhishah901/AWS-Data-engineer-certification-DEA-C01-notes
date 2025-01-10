---
title: Partitions
updated: 2024-11-11 02:15:47Z
created: 2024-11-11 02:15:34Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

In Amazon DynamoDB, data is distributed across multiple partitions based on the partition key. Each partition can handle a certain amount of read and write capacity. 

If the workload is not evenly distributed across partitions, some partitions (known as “hot” partitions) may receive a higher volume of traffic than others, leading to throttling and inefficient use of provisioned capacity