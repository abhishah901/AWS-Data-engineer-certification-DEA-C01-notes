# AWS Backup

## What It Is
Centralized backup service for AWS resources

## Supports
- EBS volumes
- EC2 instances
- RDS databases
- DynamoDB tables
- EFS file systems
- FSx file systems
- Storage Gateway volumes
- Aurora clusters
- Neptune
- DocumentDB

## Key Components

**Backup Plans:**
- Schedule (daily, weekly, monthly)
- Retention period
- Lifecycle rules (cold storage)
- Copy to other regions/accounts

**Backup Vault:**
- Storage container for backups
- Encryption (KMS)
- Access policies
- Lock (prevent deletion)

**Resource Assignment:**
- Tags (backup all with tag "Backup:Daily")
- Resource IDs
- Resource types

## Features

**Cross-region copy:** Disaster recovery
**Cross-account copy:** Centralized backup account
**Point-in-time recovery:** Restore to specific time
**Compliance:** Backup policies enforcement

## vs Native Snapshots

**AWS Backup:**
- Centralized management
- Multiple resource types
- Automated lifecycle
- Cross-account/region
- Compliance reporting

**Native (EBS snapshots, RDS snapshots):**
- Per-service management
- Manual or custom automation
- More control per resource

## Exam Signals
"Centralized backup"
"Multiple AWS services"
"Backup compliance"
"Cross-region DR"
"Automated retention"