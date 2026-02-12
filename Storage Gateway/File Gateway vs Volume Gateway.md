# File Gateway vs Volume Gateway

## File Gateway
**NFS/SMB file shares backed by S3**

**Protocol:** NFS, SMB
**Storage:** S3 (files as objects)
**Access:** File-level
**Use cases:**
- File shares
- Backups/archives
- Content distribution
- Migrate file servers to S3

**On-prem view:** Network file share
**AWS view:** S3 objects

## Volume Gateway
**iSCSI block storage backed by S3**

**Protocol:** iSCSI
**Storage:** S3 (EBS snapshots)
**Access:** Block-level

**Two modes:**

**Stored Volumes:**
- Full copy on-premises
- Async backup to S3
- Low latency (local data)

**Cached Volumes:**
- Frequently accessed on-prem (cache)
- Full copy in S3
- Lower on-prem storage

**Use cases:**
- Block storage for apps
- Database backups
- DR with EBS restore

## Key Differences

| Feature | File Gateway | Volume Gateway |
|---------|--------------|----------------|
| Protocol | NFS/SMB | iSCSI |
| Type | File | Block |
| Storage | S3 objects | S3 (snapshots) |
| Use | File shares | Databases, apps |
| AWS restore | Direct S3 | EBS from snapshot |

**Decision:** Files/shares → File Gateway. Block storage/databases → Volume Gateway.