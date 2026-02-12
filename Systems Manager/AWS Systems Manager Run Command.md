# AWS Systems Manager Run Command

## What It Is
Execute commands on EC2 instances or on-premises servers remotely without SSH/RDP

## Core Concept
Run scripts/commands across fleet of instances from console/CLI/API

## Key Features

**No SSH/RDP needed:**
- No bastion hosts
- No key management
- No open ports

**Scale:**
- Single instance or thousands
- Target by tags, resource groups, or manually

**Built-in Documents:**
- AWS-RunShellScript (Linux)
- AWS-RunPowerShellScript (Windows)
- AWS-UpdateSSMAgent
- AWS-ConfigureAWSPackage
- Hundreds of pre-built documents

## Requirements

**SSM Agent:**
- Must be installed on instances
- Pre-installed on Amazon Linux, Ubuntu, Windows AMIs
- For on-premises: Install agent + create hybrid activation

**IAM Role:**
- Instance needs role with AmazonSSMManagedInstanceCore policy
- Allows agent to communicate with SSM

**Network:**
- Outbound HTTPS (443) to SSM endpoints
- No inbound ports needed

## How It Works

1. Send command via console/CLI/API
2. SSM service queues command
3. Agent polls SSM (or receives via EventBridge)
4. Agent executes command
5. Output sent back to SSM
6. View results in console/CloudWatch Logs

## Common Use Cases

- Patch instances (run update commands)
- Install/remove software
- Run configuration scripts
- Gather inventory
- Execute one-time administrative tasks
- Automated remediation (via EventBridge + Lambda)

## Targeting

**By tags:**
Target instances with tag "Environment:Production"

**By resource group:**
Target all instances in specific resource group

**Manual:**
Select specific instance IDs

**All instances:**
Target entire fleet

## Output

**Command output:**
- Stored in SSM for limited time
- Send to S3 bucket (long-term)
- Send to CloudWatch Logs
- View in console

**Status:**
- Success
- Failed
- Timed out
- In progress

## Integration Patterns

**EventBridge trigger:**
S3 upload → EventBridge → Run Command (process file)

**Config remediation:**
Non-compliant resource → Config → Run Command (fix)

**Maintenance Windows:**
Schedule Run Command during maintenance window

## vs Other Tools

**Run Command:**
- Ad-hoc execution
- Immediate
- Manual or event-triggered

**State Manager:**
- Scheduled/continuous
- Maintains desired state
- Uses same documents as Run Command

**Session Manager:**
- Interactive shell access
- Real-time terminal
- Alternative to SSH/RDP

## Exam Signals

"Execute command remotely"
"No SSH access needed"
"Run script across fleet"
"Automated remediation"
"Patch instances"
"Install software remotely"

## Common Exam Pattern

Problem: Need to run command on instances without SSH
Wrong: Create Lambda to SSH into instances
Right: Systems Manager Run Command

Problem: Automate patching
Wrong: Manual SSH to each instance
Right: Run Command with AWS-RunPatchBaseline document

## Limitations

- Command timeout (default 1 hour, max 48 hours)
- Output size limits (store in S3 for large outputs)
- Rate limits on concurrent executions