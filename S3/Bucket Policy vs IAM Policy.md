# Bucket Policy vs IAM Policy

## Quick Rule
IAM = control who (identity-based)
Bucket Policy = control what can access bucket (resource-based)

## Use Bucket Policy

**Cross-account access** (required)
**Public/anonymous access** (only option)
**AWS service access** (CloudFront, ELB logs, CloudTrail)
**IP/VPC restrictions** (condition-based)
**Centralized bucket control**

## Use IAM Policy

**Same-account users/roles**
**Least privilege per identity**
**Service roles** (Lambda, EC2)

## Use Both

**Cross-account** = Bucket policy (allow account) + IAM policy (allow user)
**Defense in depth** = Both must allow

## Decision Tree

Anonymous users? → Bucket policy
Different AWS account? → Bucket policy + IAM
Same account users? → IAM policy
AWS service access? → Bucket policy
IP/VPC conditions? → Bucket policy

## Key Differences

**IAM:**
- Attached to users/roles
- Cannot do public access
- Cannot do cross-account alone

**Bucket Policy:**
- Attached to bucket
- Can do public access
- Has Principal field
- Required for cross-account

## Exam Signals

"Cross-account" → Bucket policy required
"Public access" → Bucket policy
"VPC endpoint only" → Bucket policy with condition
"CloudFront/service" → Bucket policy
"IAM user needs access" (same account) → IAM policy

## Common Traps

IAM policy alone for cross-account → Wrong (need bucket policy)
Bucket policy for internal users → Over-permissive (use IAM)