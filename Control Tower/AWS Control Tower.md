# AWS Control Tower

Automated multi-account AWS environment setup and governance.

## Purpose
Set up and govern secure, compliant multi-account AWS environment based on best practices.

## Key Features

**Landing Zone:**
- Pre-configured multi-account structure
- Organizational Units (OUs): Security, Sandbox, etc.
- Shared accounts (Log Archive, Audit)
- Identity management (SSO)

**Guardrails:**
- **Preventive:** SCPs that prevent actions
- **Detective:** Config Rules that detect violations
- Mandatory, strongly recommended, elective

**Account Factory:**
- Automated account provisioning
- Standardized account baselines
- Self-service via Service Catalog

**Dashboard:**
- Centralized governance view
- Compliance status
- Account inventory

## Account Structure
```
Root
├── Security OU
│   ├── Log Archive Account
│   └── Audit Account
├── Sandbox OU
│   └── User accounts
└── Production OU
    └── Production accounts
```

## Guardrail Examples

**Preventive:**
- Disallow public S3 buckets
- Require MFA for root
- Restrict regions

**Detective:**
- Detect unencrypted EBS volumes
- Detect public RDS snapshots

## vs AWS Organizations

| Feature | Control Tower | Organizations |
|---------|---------------|---------------|
| Setup | Automated best practices | Manual setup |
| Guardrails | Built-in | Manual SCPs |
| Landing Zone | Pre-configured | Build yourself |
| Complexity | Easier | More flexible |

**Control Tower = Organizations + automation + best practices**

## Use Cases
- New AWS multi-account setup
- Enforce compliance at scale
- Standardized account provisioning
- Enterprise governance

**When to use:** Starting fresh or need automated governance. If already have complex Org setup, may not fit.