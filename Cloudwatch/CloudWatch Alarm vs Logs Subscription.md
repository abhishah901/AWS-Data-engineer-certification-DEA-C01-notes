# CloudWatch Alarm vs Logs Subscription

## CloudWatch Alarm
**Triggers on metric thresholds**

**Data source:** CloudWatch Metrics
**Example:** CPU > 80%, error count > 10

**Triggers:**
- SNS notification
- Auto Scaling action
- EC2 action (stop/terminate/reboot)
- Systems Manager action

**Use:** Metric-based monitoring and automated responses

## CloudWatch Logs Subscription
**Filters and streams log data in real-time**

**Data source:** CloudWatch Logs
**Example:** Specific text in logs ("SSH login", "ERROR", "Failed authentication")

**Destinations:**
- Lambda (process/analyze)
- Kinesis Data Firehose (archive to S3)
- Kinesis Data Streams (real-time processing)
- OpenSearch (search/visualization)

**Use:** Log pattern matching, real-time log processing

## Key Differences

| Feature | Alarm | Logs Subscription |
|---------|-------|-------------------|
| Source | Metrics | Logs |
| Trigger | Threshold breach | Pattern match |
| Granularity | Aggregate data | Individual log events |
| Actions | Limited (SNS, ASG, EC2) | Flexible (Lambda) |

## Example Scenarios

**Alarm:**
"Alert when error rate > 5% over 5 minutes" → Metric-based

**Logs Subscription:**
"Trigger Lambda when 'SSH login' appears in logs" → Pattern-based

## Decision Guide
- **Metric threshold** → CloudWatch Alarm
- **Log pattern/content** → Logs Subscription
- **Immediate log processing** → Logs Subscription + Lambda

**For SSH detection:** Logs Subscription (looking for text pattern in logs, not metric).