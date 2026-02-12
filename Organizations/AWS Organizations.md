# AWS Organizations

Centrally manage multiple AWS accounts.

## Structure
```
Root (Organization)
├── OU: Production
│   ├── Account A
│   └── Account B
└── OU: Development
    └── Account C
```

**Root:** Top-level container
**OU (Organizational Unit):** Groups of accounts
**Accounts:** Individual AWS accounts

## Key Features

**Consolidated Billing**
- Single payment for all accounts
- Volume discounts aggregate across accounts
- Reserved Instance sharing

**Service Control Policies (SCPs)**
- Permission boundaries for accounts/OUs
- Restricts what IAM users/roles can do
- Does NOT grant permissions (only limits)

**Account Management**
- Create accounts programmatically
- Centralized CloudTrail/Config
- Tag policies for governance

## SCP Example
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Deny",
    "Action": "ec2:*",
    "Resource": "*",
    "Condition": {
      "StringNotEquals": {
        "ec2:Region": ["us-east-1", "us-west-2"]
      }
    }
  }]
}
```
Denies EC2 actions outside specified regions.

## Common Patterns
- Dev/Test/Prod account separation
- Department/team isolation
- Security/compliance enforcement
- Cost allocation by OU/account

## Integration
- AWS Config aggregators (multi-account compliance)
- CloudFormation StackSets (deploy across accounts)
- SSO (centralized access)