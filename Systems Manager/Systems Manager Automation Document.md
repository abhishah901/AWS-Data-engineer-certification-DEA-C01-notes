# Systems Manager Automation Document

Pre-defined or custom workflows to automate operational tasks.

## What It Is
- Runbook defining steps to execute
- JSON/YAML format
- Can orchestrate multiple AWS services

## Document Types
- **AWS-owned:** Pre-built (e.g., `AWS-RestartEC2Instance`)
- **Custom:** User-created workflows

## Common Actions
- Start/stop/restart EC2 instances
- Create AMIs/snapshots
- Patch instances
- Run Lambda functions
- Execute Run Command documents
- Invoke AWS APIs

## Example Use Cases
- Automated remediation (restart unhealthy instance)
- Scheduled maintenance
- Disaster recovery workflows
- Compliance enforcement

## Triggers
- Manual execution
- EventBridge (scheduled or event-based)
- Config Rules (auto-remediation)
- Maintenance Windows

## Key Features
- Multi-step workflows
- Conditional logic
- Error handling
- Approval steps
- Parameter passing

**vs Run Command:** Run Command executes single commands. Automation orchestrates multi-step workflows across services.