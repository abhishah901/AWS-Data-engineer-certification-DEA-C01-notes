# CloudWatch Detailed Monitoring

High-frequency metric collection for EC2 instances.

## Basic vs Detailed

**Basic (Default):**
- Free
- 5-minute intervals
- Limited metrics

**Detailed:**
- Additional cost ($2.10/month per instance)
- 1-minute intervals
- Same metrics, higher frequency

## Enable
```bash
# At launch
aws ec2 run-instances --monitoring Enabled=true

# Existing instance
aws ec2 monitor-instances --instance-ids i-1234567890abcdef0
```

## Use Cases
- Faster auto-scaling response (1-min vs 5-min data)
- Quick anomaly detection
- Fine-grained performance monitoring
- Critical production workloads

## Metrics Available
CPU, Network, Disk (same as basic, just more frequent)

**Note:** Memory/disk space NOT included (need CloudWatch Agent for those)

**Decision:** Use for critical instances needing rapid auto-scaling. Not needed for most workloads.