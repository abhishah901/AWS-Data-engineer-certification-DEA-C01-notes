# Trusted Advisor Notifications

Automated alerts for Trusted Advisor check status changes.

## Features

**Weekly Email Notifications:**
- Summary of check results
- Available for Business/Enterprise Support

**CloudWatch Events (EventBridge):**
- Real-time notifications on check changes
- Trigger automated responses

**AWS Health Dashboard Integration:**
- View Trusted Advisor events

## EventBridge Integration
```yaml
# Example: Alert on exposed access keys
Event Pattern:
  source: aws.trustedadvisor
  detail-type: Trusted Advisor Check Item Refresh Notification
  detail:
    status: ERROR
    check-name: Exposed Access Keys
```

## Use Cases
- Alert on security issues (exposed keys, open security groups)
- Auto-remediate (Lambda fixes issues)
- Cost optimization alerts
- Service limit warnings

## Setup
Business/Enterprise Support → Enable notifications in Trusted Advisor console

**vs Manual Checks:** Proactive notifications instead of manual dashboard reviews.