---
title: Sharding
updated: 2024-12-24 20:31:20Z
created: 2024-11-09 04:55:57Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon Kinesis Data Streams supports resharding, which lets you adjust the number of shards in your stream to adapt to changes in the rate of data flow through the stream. 

Resharding is considered an advanced operation.
 
There are two types of resharding operations: shard split and shard merge.

- shard split: you divide a single shard into two shards. 
- shard merge: you combine two shards into a single shard.

Resharding is always pairwise in the sense that you cannot split into more than two shards in a single operation, and you cannot merge more than two shards in a single operation.

The shard or pair of shards that the resharding operation acts on are referred to as parent shards. The shard or pair of shards that result from the resharding operation are referred to as child shards.

The `SplitShard` command is used to increase the number of shards in a Kinesis data stream, which can help handle increased data volume. Each shard in a Kinesis data stream provides a fixed amount of capacity, so adding more shards increases the stream’s capacity to ingest and transport data.


