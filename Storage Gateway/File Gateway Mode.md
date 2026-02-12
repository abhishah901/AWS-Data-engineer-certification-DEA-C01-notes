# File Gateway Mode

## What It Is
Network file share (NFS/SMB) backed by S3.

## How It Works
- Files stored as objects in S3
- Local cache for frequently accessed files
- POSIX metadata preserved
- Async upload to S3

## Architecture
```
On-prem apps → File Gateway (NFS/SMB) → S3
                    ↓
              Local cache
```

## Key Features
- S3 storage classes support
- S3 lifecycle policies
- Versioning
- Cross-region replication
- Encryption

## Use Cases
- Cloud-backed file shares
- Archive/backup to S3
- Migrate file servers to cloud
- Disaster recovery

## Access
- On-prem: Via File Gateway (low latency)
- Cloud: Direct S3 access
- Both can access same data

## vs Other Gateways
- **File:** NFS/SMB to S3
- **Volume:** iSCSI block storage
- **Tape:** VTL for backups