# Amazon GuardDuty

Intelligent threat detection service using ML to identify malicious activity.

## What It Monitors
- VPC Flow Logs
- CloudTrail event logs
- DNS logs
- S3 data events
- EKS audit logs
- RDS login activity

## Threat Detection
- Compromised instances (cryptocurrency mining, backdoors)
- Reconnaissance (port scanning, unusual API calls)
- Account compromise (leaked credentials, unusual logins)
- Malware, ransomware
- Data exfiltration

## How It Works
- Continuous monitoring (no agent needed)
- ML models analyze behavior
- Generates findings (Low, Medium, High severity)
- Near real-time alerts

## Integration
- EventBridge (automated response)
- Security Hub (centralized view)
- SNS notifications
- Lambda for remediation

## Enable
One-click enable per region or organization-wide.

## Pricing
Based on volume of logs analyzed (GB processed).

## vs Inspector
**GuardDuty:** Threat detection (malicious activity)
**Inspector:** Vulnerability assessment (CVEs, misconfigurations)

**Use:** Continuous threat monitoring with minimal setup.