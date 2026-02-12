# Systems Manager Hybrid Activations

Registers on-premises servers or VMs with AWS Systems Manager for management.

## Purpose
Manage non-AWS infrastructure (on-prem, other clouds) using Systems Manager.

## How It Works

**Activation process:**
1. Create activation in Systems Manager console/CLI
2. Receive activation code + activation ID
3. Install SSM Agent on server
4. Register server using activation credentials
5. Server appears as managed instance

**Result:** On-prem servers managed like EC2 instances

## What You Get

**After activation:**
- Run Command
- Patch Manager
- Session Manager
- State Manager
- Inventory collection
- Parameter Store access

**Managed instances show with `mi-` prefix** (vs `i-` for EC2)

## Activation Components

**Activation code:**
- One-time use credential
- Expires after specified time
- Used during agent registration

**Activation ID:**
- Identifies the activation
- Links instances to AWS account

**IAM role:**
- Permissions for managed instances
- Typically `AmazonSSMManagedInstanceCore` policy

## Use Cases

**Hybrid environments:**
- On-premises data centers
- VMware vCenter servers
- Other cloud providers (Azure, GCP)
- Edge locations
- Physical servers

## Limitations

**Activation limits:**
- Default: 1000 activations per account per region
- Can be increased via service quota

**Expiration:**
- Activations expire after set time (default 24 hours)
- Can configure up to 30 days
- Expired activations can't register new instances

## IAM Role Requirements

**Role needs:**
- Trust policy for SSM service
- Permissions to call Systems Manager APIs
- Typically use AWS managed policy

## Pricing

**Managed instances:**
- On-demand: Pay per instance per hour
- Standard tier: Free up to 1000 instances
- Advanced tier: Paid, more features

## Managed Instance vs EC2 Instance

| Feature | Managed (on-prem) | EC2 |
|---------|-------------------|-----|
| Prefix | mi- | i- |
| Registration | Activation | Automatic (IAM role) |
| Network | Outbound HTTPS | VPC |
| Billing | Standard/Advanced tier | Included with EC2 |

## Common Pattern

**Hybrid patching:**
1. Create activation
2. Install SSM Agent on servers
3. Register with activation code
4. Use Patch Manager for all servers (AWS + on-prem)

**Single pane of glass for infrastructure management**