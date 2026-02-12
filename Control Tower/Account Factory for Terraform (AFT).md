# Account Factory for Terraform (AFT)

Automates AWS account provisioning using Terraform in Control Tower environments.

## Purpose
Provision and customize AWS accounts at scale using Terraform (alternative to Service Catalog-based Account Factory).

## Key Features

**Terraform-based:**
- Define accounts as code
- Version control
- GitOps workflow

**Account Customization:**
- Apply Terraform modules after account creation
- Network setup, IAM roles, baselines
- Account-specific or global customizations

**Pipeline:**
- Account request via Git
- Automated provisioning
- Continuous customization updates

## Architecture
```
Git Repo → CodePipeline → AFT → Control Tower → New Account
                                      ↓
                              Apply Terraform customizations
```

## Feature Flags
Built-in capabilities:
- `aft_feature_enterprise_support` - Auto-enable Enterprise Support
- `aft_feature_cloudtrail_data_events` - Enable data events
- `aft_feature_delete_default_vpc` - Remove default VPCs

## vs Standard Account Factory

| Feature | AFT | Account Factory |
|---------|-----|-----------------|
| Tool | Terraform | Service Catalog |
| Customization | Terraform modules | Limited |
| Version Control | Git | N/A |
| Workflow | GitOps | Console/API |
| Flexibility | High | Lower |

## Use Cases
- Large-scale account provisioning
- Complex account customization
- Infrastructure as Code preference
- GitOps workflows

**When to use:** Need Terraform-based, customizable, version-controlled account provisioning at scale.