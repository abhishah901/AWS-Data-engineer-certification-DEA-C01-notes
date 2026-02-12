# Lustre

High-performance parallel file system for compute-intensive workloads.

## Characteristics
- Sub-millisecond latency
- Hundreds of GB/s throughput
- Millions of IOPS
- POSIX-compliant

## FSx for Lustre
AWS managed Lustre service integrated with S3.

**Deployment Types:**
- **Scratch:** Temporary, no replication, lowest cost
- **Persistent:** Replicated within AZ, durable

**S3 Integration:**
- Link to S3 bucket
- Lazy load: Files loaded on first access
- Export: Write results back to S3

## Use Cases
- HPC simulations
- Machine learning training
- Video rendering
- Financial modeling
- Genomics analysis

## When to Use
Need fastest file system performance for compute-intensive batch processing jobs, especially with large datasets in S3.