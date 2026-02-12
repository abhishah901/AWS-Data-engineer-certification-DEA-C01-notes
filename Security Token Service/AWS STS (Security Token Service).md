# AWS STS (Security Token Service)

Provides temporary security credentials for accessing AWS resources.

## Core Function
Issues short-term credentials instead of long-term IAM user credentials.

## Key Operations

**AssumeRole:**
- Assume IAM role to get temporary credentials
- Used by services, cross-account access, federated users
- Most common STS operation

**AssumeRoleWithSAML:**
- For federated users via SAML 2.0
- Enterprise SSO integration (Active Directory, Okta)

**AssumeRoleWithWebIdentity:**
- For web/mobile apps using identity providers
- Google, Facebook, Amazon login

**GetSessionToken:**
- MFA-protected API calls
- Temporary credentials for IAM users

## How It Works
```
User/Service → STS AssumeRole → Temporary credentials
                                  ↓
                            Access AWS resources
```

## Temporary Credentials Include
- Access Key ID
- Secret Access Key
- Session Token
- Expiration (15 min to 12 hours)

## Use Cases
- Cross-account access
- EC2 instance roles
- Lambda execution roles
- Federated access (SSO)
- Mobile app authentication
- Systems Manager managed instances

**In SSM context:** On-premises servers assume role via STS to authenticate with Systems Manager.