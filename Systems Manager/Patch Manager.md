AWS Systems Manager Patch Manager automates the process of patching managed instances with both security-related and other types of updates. 

You can use the Patch Manager to apply patches for both operating systems and applications. (On Windows Server, application support is limited to updates for Microsoft applications.) You can patch fleets of Amazon EC2 instances or your on-premises servers and virtual machines (VMs) by operating system type. This includes supported versions of Windows Server, Ubuntu Server, Red Hat Enterprise Linux (RHEL), SUSE Linux Enterprise Server (SLES), CentOS, Amazon Linux, and Amazon Linux 2.

You can scan instances to see only a report of missing patches, or you can scan and automatically install all missing patches.

Patch Manager uses patch baselines, which include rules for auto-approving patches within days of their release, as well as a list of approved and rejected patches. You can install patches on a regular basis by scheduling patching to run as a Systems Manager maintenance window task. You can also install patches individually or to large groups of instances by using Amazon EC2 tags. You can add tags to your patch baselines themselves when you create or update them.
# AWS Systems Manager Patch Manager

Automates OS and application patching for EC2/on-premises instances.

## Core Components

**Patch Baseline**
- Defines which patches to approve
- Auto-approval delay (e.g., 7 days)
- Filter by classification/severity
- AWS-managed or custom

**Patch Groups**
- Tag instances: `Patch Group = Production`
- Assign baseline to group

**Maintenance Windows**
- Schedule patching operations
- Define duration, targets, tasks

**Compliance**
- Reports missing patches
- Integration with Config/CloudWatch

## Operations

**Scan** - Check for missing patches
**Install** - Apply approved patches
**Scan and Install** - Combined

## Example Baseline
```yaml
ApprovalRules:
  - PatchFilterGroup:
      - Key: CLASSIFICATION
        Values: [Security]
      - Key: SEVERITY
        Values: [Critical]
    ApproveAfterDays: 0
```

## Maintenance Window
```yaml
Schedule: cron(0 2 ? * SUN *)
Targets:
  - Key: tag:Patch Group
    Values: [Production]
Tasks:
  - DocumentName: AWS-RunPatchBaseline
    Parameters:
      Operation: Install
      RebootOption: RebootIfNeeded
```

## Exam Scenarios

**"Automate patching"** → Patch Manager + Maintenance Windows
**"Only critical patches within 24h"** → Custom baseline, ApproveAfterDays: 0
**"Different schedules per environment"** → Patch Groups
**"Block specific patches"** → Rejected list in baseline
**"Compliance reporting"** → Patch Manager compliance + Config