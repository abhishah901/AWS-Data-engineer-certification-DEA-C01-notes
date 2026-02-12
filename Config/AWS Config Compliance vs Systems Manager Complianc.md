# AWS Config Compliance vs Systems Manager Compliance

## AWS Config
**What:** Tracks AWS resource configuration compliance

**Scope:**
- AWS resource configurations
- Configuration changes over time
- Compliance against Config Rules

**Examples:**
- S3 bucket encryption enabled
- EC2 in approved VPC
- IAM password policy enforced
- Security group rules

**Data source:** AWS API calls (CloudTrail)

## Systems Manager Compliance
**What:** Tracks patch and association compliance on instances

**Scope:**
- Patch compliance (missing patches)
- Association compliance (State Manager)
- Custom compliance (user-defined)
- Inventory data

**Examples:**
- Missing security patches
- Outdated software versions
- Failed configuration associations
- Antivirus status

**Data source:** SSM Agent on instances

## Key Difference
- **Config:** Resource configuration compliance (infrastructure)
- **SSM:** Instance-level compliance (OS, patches, software)

## Integration
Often used together - Config for infrastructure, SSM for instance health/patching.