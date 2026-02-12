# AWS Config - Managed Rules

Pre-built compliance rules to evaluate AWS resource configurations.

## What They Are
AWS-provided Config Rules for common compliance checks (no custom Lambda needed).

## Examples

**Security:**
- `encrypted-volumes` - EBS volumes encrypted
- `s3-bucket-public-read-prohibited` - No public S3 buckets
- `iam-password-policy` - IAM password requirements
- `root-account-mfa-enabled` - Root has MFA

**Compliance:**
- `approved-amis-by-id` - Only approved AMIs used
- `ec2-instance-managed-by-ssm` - Instances have SSM agent
- `rds-multi-az-support` - RDS has Multi-AZ enabled

**Best Practices:**
- `ec2-instance-no-public-ip` - No public IPs on instances
- `dynamodb-autoscaling-enabled` - DynamoDB uses auto-scaling



## Auto-Remediation
Pair with SSM Automation Documents for automatic fixes.

**Example:**
```
Rule: encrypted-volumes
Non-compliant: Unencrypted EBS volume
Remediation: SSM doc creates encrypted snapshot + new volume
```

## vs Custom Rules
**Managed:** Pre-built, AWS-maintained, simple setup
**Custom:** Lambda function, your logic, more flexibility

**Use managed rules for:** Common compliance scenarios (most cases)