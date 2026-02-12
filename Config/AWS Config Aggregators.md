# AWS Config Aggregators

Collects AWS Config data from multiple accounts and regions into a single account.

## Purpose
- Centralized compliance view across organization
- Multi-account/multi-region configuration visibility
- Security and audit at scale

## Setup
**Source accounts:** Enable AWS Config
**Aggregator account:** Create aggregator, specify source accounts/regions

## Authorization
- **Individual accounts:** Manual authorization per account
- **AWS Organizations:** Automatic authorization for all accounts

## Features
- View compliance across accounts
- Search resources across organization
- Aggregate rules and remediation
- CloudWatch dashboards for org-wide metrics

## Use Cases
- Enterprise compliance reporting
- Security posture monitoring
- Resource inventory across organization
- Multi-account governance

## Key Points
- Read-only view (doesn't modify configs)
- Updates near real-time
- One aggregator can handle 10,000+ accounts