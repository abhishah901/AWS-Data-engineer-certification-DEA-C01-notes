# AWS Health

Provides visibility into AWS service health and account-specific events.

## Components

**AWS Health Dashboard (Service Health)**
- Global AWS service status
- Public view (status.aws.amazon.com)
- Regional service availability
- Historical information

**AWS Personal Health Dashboard**
- Account-specific events
- Scheduled maintenance
- Resource-specific notifications
- Proactive notifications

## Event Types

**Service Events:**
- AWS service disruptions
- Regional outages
- Degraded performance

**Account Events:**
- Scheduled maintenance on your resources
- Security notifications
- Billing alerts
- Resource changes

## Integration

**EventBridge:**
```yaml
# Trigger Lambda on health event
Source: aws.health
DetailType: AWS Health Event
```

**Use Cases:**
- Automated responses to health events
- Restart instances during maintenance
- Notify teams via SNS/Slack
- Create support tickets

## API Access

**AWS Health API:**
- Programmatic access to health events
- Requires Business or Enterprise Support
- Query events, affected resources

## Example EventBridge Rule
```json
{
  "source": ["aws.health"],
  "detail-type": ["AWS Health Event"],
  "detail": {
    "eventTypeCategory": ["scheduledChange"]
  }
}
```

**Common Pattern:** Health Event → EventBridge → Lambda → Auto-remediation/notification

**Use:** Proactive monitoring and automated response to AWS service issues affecting your resources.