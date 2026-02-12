# SCPs and OUs

## Service Control Policies (SCPs)

**What they are:**
Permission boundaries for AWS Organizations that set maximum permissions.

**Key principle:**
SCPs don't grant permissions - they limit what can be done, even with IAM permissions.

## Where SCPs Can Be Attached

**Valid attachment points:**
1. Organization root (affects all accounts)
2. Organizational Units (OUs) (affects accounts in OU)
3. Individual member accounts



## Organizational Units (OUs)

**Structure:**
```
Organization Root
├── Production OU
│   ├── Account A
│   └── Account B
├── Development OU
│   ├── Account C
│   └── Account D
└── Finance OU
    └── Account E
```

**OUs group accounts for:**
- Common policies
- Shared governance
- Administrative boundaries

## SCP Inheritance

**How it works:**
SCPs inherit down the organizational tree.

**Example:**
```
Root (SCP: Deny delete S3)
└── Production OU (SCP: Deny us-west-2)
    └── Account A (SCP: Deny EC2 termination)
```

**Account A has all three restrictions:**
- Can't delete S3 (from root)
- Can't use us-west-2 (from OU)
- Can't terminate EC2 (from account)

**Most restrictive wins**

## Common SCP Patterns

**At Root:**
- Global restrictions (all accounts)
- Region restrictions
- Critical service protections

**At OU:**
- Environment-specific (prod vs dev)
- Department-specific
- Workload-specific

**At Account:**
- Account-specific exceptions
- Granular controls

## SCP vs IAM Policies

**IAM policy:**
```json
{
  "Effect": "Allow",
  "Action": "s3:*",
  "Resource": "*"
}
```
User CAN do S3 actions (if SCP allows)

**SCP:**
```json
{
  "Effect": "Deny",
  "Action": "s3:DeleteBucket",
  "Resource": "*"
}
```
Account CANNOT delete buckets (even with IAM allow)

**Effective permissions = IAM ∩ SCP**

## Default SCP

**FullAWSAccess:**
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": "*",
    "Resource": "*"
  }]
}
```

**Attached by default to root**
**Must be present for accounts to work**

## Deny vs Allow Strategies

**Deny list (recommended):**
- FullAWSAccess attached
- Add deny SCPs for restrictions
- Easier to manage

**Allow list:**
- Remove FullAWSAccess
- Explicitly allow each service
- More restrictive, harder to manage

## SCP Limitations

**SCPs do NOT affect:**
- Management account (root account)
- Service-linked roles
- Some AWS service operations

**SCPs only limit:**
- Member account principals
- IAM users/roles in member accounts

## Common Use Cases

**Region restriction:**
Deny all except specific regions

**Service restriction:**
Deny specific AWS services

**Action restriction:**
Deny dangerous actions (delete, terminate)

**Compliance:**
Enforce organizational policies

## Exam Tips

**Remember:**
- SCPs = permission boundaries, not grants
- Attach to: root, OUs, accounts
- NOT to: users, roles, groups
- Inherit down tree
- Management account exempt