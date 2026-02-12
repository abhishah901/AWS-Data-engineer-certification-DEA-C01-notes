# CloudWatch Synthetics

Creates canaries to monitor endpoints and APIs by simulating user actions.

## Purpose
Proactively test applications 24/7 by running scheduled scripts.

## Canary Types

**Heartbeat Monitor:**
- Check endpoint availability
- Load URL, verify response

**API Canary:**
- Test REST APIs
- Verify responses, status codes

**Broken Link Checker:**
- Crawl website for broken links

**Visual Monitoring:**
- Take screenshots, compare over time
- Detect UI changes

**Custom:**
- Write Node.js/Python scripts
- Complex workflows (login, checkout)

## How It Works
1. Define canary script (what to test)
2. Set schedule (every X minutes)
3. Canary runs in Lambda
4. Results stored in S3
5. CloudWatch metrics/alarms created

## Example Use Cases
- Monitor login flow works
- Verify API returns 200
- Check critical pages load
- Detect broken checkout process
- Alert before users notice issues

## Metrics
- Success/failure rate
- Duration
- Screenshots (visual changes)
- HAR files (network activity)

## Integration
- CloudWatch Alarms (alert on failures)
- SNS notifications
- Lambda for remediation

**vs Route 53 health checks:** Synthetics runs complex workflows. Route 53 checks simple endpoint availability.