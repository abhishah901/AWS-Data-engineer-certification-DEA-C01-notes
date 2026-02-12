# AWS Service Catalog

Self-service portal for approved AWS resources.

## Purpose
Centrally manage and deploy approved IT services (CloudFormation templates).

## Key Concepts

**Products:**
- CloudFormation templates
- Versioned configurations
- Pre-approved resources (EC2, RDS, etc.)

**Portfolios:**
- Collection of products
- Access control (who can launch what)

**Constraints:**
- Launch constraints (IAM role to use)
- Template constraints (allowed parameters)
- Notification constraints (SNS)

## Workflow
1. Admin creates products (CFN templates)
2. Admin organizes into portfolios
3. Admin grants users access to portfolios
4. Users launch products via self-service

## Benefits
- Governance (only approved configurations)
- Consistency across organization
- Self-service for users (no admin needed)
- Cost control (pre-approved sizes/types)
- Compliance enforcement

## Use Cases
- Standardized environments (dev/test/prod)
- Multi-account deployments
- Enforce security policies
- Budget control

**Example:** HR team can launch approved EC2 instances without knowing CloudFormation, admin ensures instances meet security standards.