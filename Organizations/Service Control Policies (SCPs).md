# Service Control Policies (SCPs)

Permission boundaries for AWS Organizations - define maximum allowed permissions.

## Key Concept
**SCPs DENY, IAM GRANTS**
- Effective permission = IAM ∩ SCP
- Both must allow for action to work

## Scope
- Apply to accounts/OUs (not management account)
- Affect all users/roles including root
- Inherited down OU tree

## Common Uses
- Region restrictions
- Block specific services
- Prevent leaving organization
- Require encryption
- Compliance enforcement

**Remember:** SCPs restrict maximum permissions, don't grant anything.