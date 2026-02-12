# AWS EventBridge Triggers

## AWS Service Events
- EC2 instance state changes
- ECS task state changes
- RDS events (backups, failovers)
- S3 object events (via EventBridge integration)
- Auto Scaling events
- CodePipeline/CodeBuild/CodeDeploy state changes
- Lambda function invocations
- Step Functions executions
- Systems Manager parameter changes
- CloudWatch alarms
- Config rule compliance changes
- Security Hub findings
- GuardDuty findings
- Health events (AWS Health Dashboard)

## Scheduled Events
- Cron expressions
- Rate expressions (every X minutes/hours/days)

## Custom Events
- Custom application events
- Third-party SaaS events (Zendesk, Datadog, etc.)
- Partner integrations

## AWS API Calls (via CloudTrail)
- Any AWS API call (CreateInstance, DeleteBucket, etc.)
- Console sign-in events
- IAM changes

## Key Point
EventBridge can detect virtually any AWS service state change, API call, or scheduled event.