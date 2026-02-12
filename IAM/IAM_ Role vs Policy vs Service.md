# IAM: Role vs Policy vs Service

## IAM Policy

**What:** Document defining permissions (JSON)
**Contains:** Allow/Deny statements for actions on resources
**Standalone:** No, must attach to identity or resource

**Example:**
{
  "Effect": "Allow",
  "Action": "s3:GetObject",
  "Resource": "arn:aws:s3:::bucket/*"
}

## IAM Role

**What:** Identity that can be assumed
**Has:** Trust policy (who can assume) + permission policies (what they can do)
**Used by:** AWS services, users, applications

**Two parts:**
1. Trust policy: "EC2 can assume this role"
2. Permission policy: "Role can read S3"

**Example use:**
EC2 instance assumes role → Gets temporary credentials → Access S3

## IAM User

**What:** Permanent identity for person/application
**Has:** Long-term credentials (password/access keys) + policies
**Used by:** Humans, applications (not recommended for apps)

## IAM Service Role

**What:** Role specifically for AWS service
**Example:** Lambda execution role, EC2 instance role
**Trust policy:** Allows service to assume it

## Relationship

Policy = permission document
Role = identity that uses policies
User = permanent identity with policies

## When to Use

**IAM Role:**
- EC2/Lambda needs AWS access
- Cross-account access
- Temporary credentials
- Federated users

**IAM User:**
- Human accessing AWS
- Long-term credentials needed
- Console/CLI access

**IAM Policy:**
- Define what can be done
- Attach to roles/users/groups/resources

## Key Differences

**Role:**
- Assumable
- Temporary credentials
- No password/keys
- For services or temporary use

**User:**
- Permanent identity
- Long-term credentials
- Has password/access keys
- For people

**Policy:**
- Not an identity
- Just permissions
- Must attach to something

## Exam Context

"EC2 needs S3 access" → IAM role (not user)
"Cross-account access" → IAM role
"Define permissions" → IAM policy
"Service needs permissions" → Service role
"Human needs access" → IAM user