# EC2Rescue Tool

Troubleshooting tool for diagnosing and fixing common EC2 instance issues.

## Platform Versions
- **EC2Rescue for Linux**
- **EC2Rescue for Windows**

## Key Functions
- Collect system logs and configuration files
- Analyze OS-level issues
- Detect common problems
- Automated remediation

## Common Issues Fixed
- Lost SSH/RDP access
- Firewall/network misconfigurations
- Disk issues (full disk, corrupt filesystem)
- Boot problems
- Performance issues
- OS patches causing problems

## How to Use

**Automated (SSM):**
```bash
# Run via Systems Manager Run Command
Document: AWSSupport-ExecuteEC2Rescue
```

**Manual:**
- Download tool
- Run on instance or offline (attach volume to another instance)

## Key Features
- Backup before remediation
- Detailed diagnostic reports
- Offline mode (attach root volume to helper instance)
- Integration with Systems Manager

## Use Cases
- Instance won't boot
- Can't SSH/RDP
- Diagnose performance degradation
- Collect logs for AWS Support

**Best Practice:** Use with Systems Manager for automated troubleshooting.