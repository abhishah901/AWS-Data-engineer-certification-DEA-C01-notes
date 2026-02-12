# Amazon FSx

Fully managed file systems for specific workloads.

## FSx Types

**FSx for Windows File Server**
- Windows-native shared file storage
- SMB protocol, Active Directory integration
- Use: Windows applications, shared drives

**FSx for Lustre**
- High-performance file system
- Optimized for HPC, ML training, video processing
- Sub-millisecond latency
- Can integrate with S3

**FSx for NetApp ONTAP**
- NetApp file system features
- Multi-protocol: NFS, SMB, iSCSI
- Use: Migrate NetApp workloads

**FSx for OpenZFS**
- Linux file system
- NFS protocol
- Point-in-time snapshots

## Key Features
- Fully managed (patching, backups)
- Multi-AZ deployment option
- Encryption at rest/transit
- VPC integration

## FSx for Lustre + S3
- Link Lustre to S3 bucket
- Fast processing of S3 data
- Write results back to S3
- Common for ML/analytics pipelines

## When to Use
- **Windows apps** → FSx for Windows
- **HPC/ML** → FSx for Lustre
- **NetApp migration** → FSx for ONTAP
- **Linux shared storage** → FSx for OpenZFS or EFS