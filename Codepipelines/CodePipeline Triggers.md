# CodePipeline Triggers

## Three Methods

**EventBridge (Events)**
- AWS services (CodeCommit, S3, ECR)
- Near real-time (seconds)
- Recommended for AWS sources

**Webhooks**
- External Git (GitHub, Bitbucket, GitLab)
- Real-time (instant)
- HTTP POST to endpoint

**Polling**
- Checks source every N minutes
- Delayed (minutes)
- Legacy/fallback only

## Decision

AWS source → EventBridge
External Git → Webhook
Last resort → Polling

## Comparison

Events: Seconds delay, AWS native
Webhooks: Instant, external services
Polling: Minutes delay, inefficient

## Exam Signals

"Real-time on commit" → Events/Webhooks
"CodeCommit" → EventBridge
"GitHub" → Webhook
"S3 upload triggers" → EventBridge
"Immediate execution" → Not polling