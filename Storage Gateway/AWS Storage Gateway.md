# AWS Storage Gateway

Hybrid cloud storage service connecting on-premises to AWS cloud storage.

## Gateway Types

**File Gateway**
- NFS/SMB file interface to S3
- Files stored as objects in S3
- Local cache for frequently accessed data
- Use: File shares, backups, content distribution

**Volume Gateway**
- iSCSI block storage backed by S3
- Two modes:
  - **Stored:** Full copy on-prem, async backup to S3
  - **Cached:** Hot data on-prem, full copy in S3
- Use: Block storage, DR, database backups

**Tape Gateway (VTL)**
- Virtual tape library interface
- Backup software compatible
- Archives to S3/Glacier
- Use: Replace physical tape infrastructure

**FSx File Gateway**
- Local cache for FSx for Windows File Server
- Low-latency access to FSx
- Use: Windows workloads, replace file servers

## Key Features
- Local caching for low-latency access
- Encryption in transit/at rest
- Integration with existing backup software
- Bandwidth throttling

## Common Pattern
On-premises apps → Storage Gateway (local cache) → S3/Glacier (cloud storage)

## Use Cases
- Hybrid cloud storage
- DR and backup
- Cloud migration
- File share consolidation