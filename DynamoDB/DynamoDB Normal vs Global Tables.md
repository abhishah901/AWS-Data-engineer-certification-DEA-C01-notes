# DynamoDB Normal vs Global Tables

## Normal (Standard) Table
**Single-region table**

- Data stored in one region
- Can create read replicas manually
- Cross-region replication requires manual setup
- Single-region access

## Global Tables
**Multi-region, multi-active replication**

- Automatically replicated across regions
- Active-active (read/write in any region)
- Sub-second replication
- Last-writer-wins conflict resolution
- Automatic failover

## Key Differences

| Feature | Normal Table | Global Table |
|---------|--------------|--------------|
| Regions | Single | Multiple |
| Writes | One region | Any region |
| Replication | Manual | Automatic |
| Conflict resolution | N/A | Last-writer-wins |
| Latency | Regional | Global low latency |
| DR | Manual failover | Automatic |

## Use Cases

**Normal Table:**
- Single-region app
- Lower cost
- No global access needed

**Global Table:**
- Global applications
- Multi-region DR
- Low latency worldwide
- Business continuity

## Setup

**Normal:** Create table

**Global:** Enable DynamoDB Streams → Add replica regions

## Pricing
Global tables cost more (replicated writes + storage in each region).