# CloudTrail vs CloudWatch

## CloudTrail
**What:** Logs AWS API calls (who did what, when)

**Purpose:** Audit, compliance, security analysis

**Captures:**
- User identity
- Time of request
- Source IP
- API action (CreateInstance, DeleteBucket)
- Parameters and responses

**Use Cases:**
- Security investigations ("who deleted this?")
- Compliance audits
- Track changes
- Detect unauthorized activity

**Storage:** S3 (optional CloudWatch Logs)

## CloudWatch
**What:** Monitors performance metrics and logs

**Purpose:** Operational monitoring, troubleshooting

**Captures:**
- Application logs
- System metrics (CPU, memory, disk)
- Custom metrics
- Performance data

**Use Cases:**
- Troubleshoot app errors
- Performance monitoring
- Set alarms on metrics
- Analyze application behavior

**Storage:** CloudWatch Logs, metrics database

## Key Difference

**CloudTrail:** WHO did WHAT (audit trail)
**CloudWatch:** HOW is system PERFORMING (monitoring)

## Example

**CloudTrail:**
"User john@company.com called TerminateInstances on i-12345 at 2pm from IP 1.2.3.4"

**CloudWatch:**
"EC2 instance CPU is 95%, application returned 500 errors, Lambda execution time 3 seconds"

## Together
Often used together - CloudTrail for compliance, CloudWatch for operations.