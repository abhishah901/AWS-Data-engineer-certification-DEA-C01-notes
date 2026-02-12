# Amazon Inspector

Automated security vulnerability assessment service.

## What It Scans
- **EC2 instances:** OS vulnerabilities, network exposure
- **Container images:** ECR images for vulnerabilities
- **Lambda functions:** Code and package dependencies

## How It Works
- Agent-based (EC2) or agentless (ECR, Lambda)
- Continuous scanning
- CVE database checks
- Network reachability analysis

## Findings
- Severity scores (Critical, High, Medium, Low)
- Remediation recommendations
- Integration with Security Hub
- EventBridge for automated responses

## Assessment Types
**Network assessments:**
- Unintended network accessibility
- Open ports

**Host assessments:**
- CVEs (Common Vulnerabilities and Exposures)
- CIS benchmarks
- Security best practices

## Use Cases
- Continuous vulnerability scanning
- Compliance (PCI-DSS, HIPAA)
- DevSecOps pipelines
- Patch management prioritization

## vs Other Services
- **GuardDuty:** Threat detection (malicious activity)
- **Inspector:** Vulnerability assessment (misconfigurations, CVEs)
- **Macie:** Data discovery/protection (sensitive data in S3)