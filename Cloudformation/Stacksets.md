# CloudFormation StackSets

Deploy CloudFormation stacks across multiple accounts and regions from single operation.

## Purpose
Create, update, or delete stacks in multiple accounts/regions simultaneously.

## Key Concepts

**StackSet:**
- Template + deployment targets
- Master definition

**Stack Instances:**
- Individual stacks in target accounts/regions
- Created from StackSet

**Deployment Targets:**
- Organizational Units (via AWS Organizations)
- Specific account IDs

## Example Use Cases
- Deploy IAM roles across all accounts
- Enable AWS Config in all regions
- Standard VPC setup for new accounts
- Security baselines organization-wide

## Permissions

**Two Models:**

**Self-managed:**
- Manual IAM role setup
- AWSCloudFormationStackSetAdministrationRole (admin account)
- AWSCloudFormationStackSetExecutionRole (target accounts)

**Service-managed (Organizations):**
- Automatic permissions
- Deploy to OUs
- No manual role setup

## Operations

**Create:**
```bash
aws cloudformation create-stack-set \
  --stack-set-name SecurityBaseline \
  --template-body file://template.yaml \
  --deployment-targets OrganizationalUnitIds=ou-abc123
```

**Update:**
All stack instances updated simultaneously

**Delete:**
Must delete stack instances first, then StackSet

## Deployment Options
- **Sequential:** One region at a time
- **Parallel:** All regions simultaneously
- **Failure tolerance:** Max failures before stopping
- **Max concurrent:** Concurrent deployments

**Use:** Multi-account/multi-region standardization at scale.