# DynamoDB Global Tables

Multi-region, multi-active database replication.

## Key Features
- Multi-region replication
- Active-active (read/write in any region)
- Sub-second replication latency
- Automatic conflict resolution (last writer wins)
- Automatic failover

## Setup
1. Enable DynamoDB Streams on table
2. Create replica in another region
3. DynamoDB handles replication

## Use Cases
- Global applications (low latency worldwide)
- Disaster recovery (multi-region)
- Business continuity
- Compliance (data residency)

## Conflict Resolution
Last write wins (based on timestamp)

## Requirements
- DynamoDB Streams enabled
- Same table name in all regions
- Same primary key structure
- Version 2019.11.21 (current version)

## Pricing
- Replicated write capacity units
- Cross-region data transfer
- Storage in each region

## vs Read Replicas (RDS)
- Global Tables: Multi-master (write anywhere)
- Read Replicas: Single-master (write one region only)