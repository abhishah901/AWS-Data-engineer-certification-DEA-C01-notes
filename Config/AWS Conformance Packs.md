# AWS Conformance Packs

Pre-packaged AWS Config rules + remediation actions deployed as one unit.

## What They Are

**Components:**
- Config rules (detect non-compliance)
- SSM Automation docs (auto-remediate)
- Deployed together as single entity

## Purpose

Deploy compliance frameworks quickly across accounts/organization.

## Key Features

**Pre-built templates:**
- CIS Benchmarks
- PCI-DSS
- NIST
- HIPAA
- Custom packs

**Automatic remediation:**
- Rule detects issue
- SSM automation fixes it
- No manual work

**Organization-wide:**
- Deploy to all accounts
- Centrally managed
- Consistent compliance

## vs Manual Config Rules

**Manual:** Create each rule individually, configure remediation separately

**Conformance pack:** Bundle rules + remediation, deploy once

## Deployment
```bash
aws configservice put-organization-conformance-pack \
  --organization-conformance-pack-name my-pack \
  --template-s3-uri s3://bucket/pack.yaml
```

## Example
```
Pack: S3 Security
├── Rule: Bucket encryption required
├── Remediation: Enable encryption
├── Rule: Block public access
└── Remediation: Enable block settings
```

## Exam Key

**"Automatic remediation" + "organization-wide" + "least overhead"**
→ Conformance packs

**vs Custom Lambda:** Conformance packs = less code, less overhead