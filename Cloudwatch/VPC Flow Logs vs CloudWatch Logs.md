# VPC Flow Logs vs CloudWatch Logs

## VPC Flow Logs

**What:**
Network traffic metadata for VPC/subnet/ENI

**Captures:**
- Source/destination IPs
- Ports
- Protocol
- Action (ACCEPT/REJECT)
- Bytes/packets

**Does NOT capture:**
- Packet contents
- Application layer data
- DNS queries (use Route 53 resolver logs)

**Use cases:**
- Troubleshoot connectivity
- Security analysis
- Traffic patterns
- Identify rejected traffic

**Destinations:**
- CloudWatch Logs
- S3
- Kinesis Data Firehose

## CloudWatch Logs

**What:**
Log aggregation service for application/system logs

**Sources:**
- EC2 instances (via CloudWatch agent)
- Lambda functions
- CloudTrail
- VPC Flow Logs
- API Gateway
- Any custom application

**Use cases:**
- Application debugging
- System monitoring
- Centralized logging
- Search/filter logs
- Create metrics from logs

## Relationship

VPC Flow Logs is a SOURCE that sends TO CloudWatch Logs

VPC Flow Logs → CloudWatch Logs (one destination option)

## Key Differences

**VPC Flow Logs:**
- Network layer (Layer 3/4)
- Traffic metadata only
- VPC-specific

**CloudWatch Logs:**
- Application layer
- Any log data
- General purpose log service

## Common Exam Pattern

"Analyze network traffic" → VPC Flow Logs
"Troubleshoot connectivity" → VPC Flow Logs
"Application logs" → CloudWatch Logs
"Security group denials" → VPC Flow Logs
"Lambda errors" → CloudWatch Logs

## Together

VPC Flow Logs sent to CloudWatch Logs, then:
- Metric filters detect patterns
- CloudWatch Alarms trigger on metrics
- Lambda for automated response