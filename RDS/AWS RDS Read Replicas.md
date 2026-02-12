Amazon RDS Read Replicas provide enhanced performance and durability for database (DB) instances. This feature makes it easy to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads. 

You can create one or more replicas of a given source DB Instance and serve high-volume application read traffic from multiple copies of your data, thereby increasing aggregate read throughput. 

Read replicas can also be promoted when needed to become standalone DB instances. 

Read replicas are available in Amazon RDS for MySQL, MariaDB, PostgreSQL, and Oracle as well as Amazon Aurora.

# RDS Read Replicas

## What They Are

Read-only copies of RDS database for scaling read traffic.

## Key Features

**Async Replication**
- Source DB replicates to replicas asynchronously
- Eventual consistency (slight lag possible)

**Scaling Reads**
- Offload read queries from primary DB
- Up to 15 read replicas per source (Aurora up to 15)
- Can chain replicas (replica of replica)

**Cross-Region**
- Create replicas in different regions
- Use for disaster recovery or local reads

**Promotion**
- Can promote replica to standalone DB
- Breaks replication link
- Use for DR failover

## Supported Engines

MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora

## Use Cases

- Read-heavy workloads (analytics, reporting)
- Disaster recovery (promote in another region)
- Reduce latency (regional read replicas)

## Key Differences: Read Replica vs Multi-AZ

| Feature | Read Replica | Multi-AZ |
|---------|--------------|----------|
| Purpose | Scale reads | High availability |
| Replication | Async | Sync |
| Accessible | Yes (read-only) | No (standby) |
| Failover | Manual promotion | Automatic |
| Cross-region | Yes | No |

## Important Points

- Each replica has own endpoint
- Application must route reads to replica endpoints
- Not for write scaling (use sharding/partitioning)
- Replication lag monitored via CloudWatch
- Charges for replicas and cross-region data transfer

# RTO and RPO with Read Replicas

## RPO (Recovery Point Objective)
**How much data loss is acceptable**

- Read Replica: Minutes (depends on replication lag)
- Async replication = some data loss possible
- Promoted replica has data up to last replicated transaction

## RTO (Recovery Time Objective)
**How long to recover**

- Read Replica: Minutes to hours
- Manual promotion required
- Need to update application endpoints
- DNS propagation time

## Comparison

| Method | RPO | RTO |
|--------|-----|-----|
| Read Replica | Minutes | Minutes-Hours (manual) |
| Multi-AZ | Seconds | 1-2 minutes (automatic) |
| Automated Backups | Hours | Hours |

## Key Points

- Read replicas NOT designed for HA (use Multi-AZ)
- Better RPO than backups, worse than Multi-AZ
- RTO slower than Multi-AZ (manual process)
- Good for DR in different region