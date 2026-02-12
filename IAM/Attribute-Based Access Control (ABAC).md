# Attribute-Based Access Control (ABAC)

## What It Is
Permissions based on attributes (tags) instead of specific resources

## Traditional (RBAC - Role-Based)
Role for Developers:
- Allow s3:* on arn:aws:s3:::dev-bucket-1
- Allow s3:* on arn:aws:s3:::dev-bucket-2
(Must update policy for each new bucket)

## ABAC
Role for Developers:
- Allow s3:* where ResourceTag/Team = ${aws:PrincipalTag/Team}

User tagged Team=Engineering → Access all resources tagged Team=Engineering
No policy updates needed for new resources

## Key Components

**Principal tags:** Tags on user/role
**Resource tags:** Tags on AWS resources
**Condition:** Match principal tag to resource tag

## Example Policy

{
  "Effect": "Allow",
  "Action": "s3:*",
  "Resource": "*",
  "Condition": {
    "StringEquals": {
      "s3:ExistingObjectTag/Department": "${aws:PrincipalTag/Department}"
    }
  }
}

User with Department=Finance → Access resources tagged Department=Finance

## Benefits

**Scalability:** No policy updates for new resources
**Least privilege:** Automatic based on tags
**Simplified management:** Tag-driven permissions

## Use Cases

- Multi-tenant environments
- Department-based access
- Project-based permissions
- Dynamic resource access

## IAM Identity Center ABAC

Map user attributes from IdP (Okta, Azure AD):
- User attribute: department=Engineering
- Access resources tagged department=Engineering

## Exam Signals

"Scale permissions without policy updates"
"Tag-based access control"
"User attributes from IdP"
"${aws:PrincipalTag/...}"
"Department-based access"
"Dynamic permissions"