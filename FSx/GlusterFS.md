# GlusterFS

Open-source distributed file system for scale-out storage.

## Key Features
- Scales to petabytes
- No metadata server (fully distributed)
- POSIX-compliant
- Replication and striping
- Self-healing

## AWS Context
- Can run on EC2 instances
- Not an AWS managed service
- Alternative: Use EFS or FSx instead

## When Mentioned in Exam
Usually in migration scenarios - "company uses GlusterFS on-premises, what AWS service to migrate to?"

**Answer:** FSx for Lustre (performance) or EFS (managed NFS)

## Key Point
GlusterFS = self-managed distributed storage. AWS alternatives are managed and typically better choices.