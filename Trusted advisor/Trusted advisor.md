- Aggregates based upon the best practices
- Learned by being trained on hundreds of thousand of AWS custommers
- Makes recommendations for
	- saving costs
	- improve availability
	- improve performance
	- close security gaps
 

# AWS Trusted Advisor

Provides real-time guidance to optimize AWS environment.

## Five Categories

**Cost Optimization**
- Idle resources (EC2, RDS, EBS)
- Underutilized instances
- Reserved Instance recommendations

**Performance**
- Over-utilized instances
- CloudFront optimizations
- EC2 to EBS throughput

**Security**
- Open security groups
- IAM use
- MFA on root account
- S3 bucket permissions
- Exposed access keys

**Fault Tolerance**
- RDS Multi-AZ
- EC2 AZ balance
- EBS snapshots
- S3 versioning

**Service Limits**
- Resource usage vs limits
- Proactive limit monitoring

## Support Tiers

**Basic/Developer:**
- 7 core checks (free)
- Security group rules, S3 permissions, IAM use, MFA, EBS snapshots, RDS backups, service limits

**Business/Enterprise:**
- Full checks (115+)
- CloudWatch integration
- Programmatic access via API
- Weekly email notifications

## Integration
- CloudWatch Events for automated responses
- AWS Config for compliance
- Service Quotas for limit increases

## Use Cases
- Security audits
- Cost reduction
- Performance tuning
- Proactive monitoring