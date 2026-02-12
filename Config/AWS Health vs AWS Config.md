# AWS Health vs AWS Config

## AWS Health
**Purpose:** Service health, lifecycle events, and planned changes

**What it monitors:**
- AWS service outages/issues
- Planned maintenance
- Version deprecations
- End-of-life announcements
- Account-specific events

**Use cases:**
- "Kubernetes version reaching EOL"
- "RDS maintenance window"
- "Service disruption in region"
- "Upcoming deprecation"

**Availability:**
- Account-specific events: Business/Enterprise support
- Global health: All customers

**Nature:** Event-driven, notifications

## AWS Config
**Purpose:** Resource configuration compliance and tracking

**What it monitors:**
- Resource configurations
- Configuration changes over time
- Compliance against rules
- Resource relationships

**Use cases:**
- "S3 bucket must be encrypted"
- "EC2 in approved subnets"
- "IAM password policy enforced"
- "Resources properly tagged"

**Availability:**
- All AWS accounts
- Pay per configuration item

**Nature:** Continuous compliance evaluation

## Key Differences

| Aspect | Health | Config |
|--------|--------|--------|
| **Focus** | Service health, lifecycle | Configuration compliance |
| **Timing** | Future events, planned | Current state, history |
| **Type** | Notifications, warnings | Compliance checks |
| **Scope** | Service-level changes | Resource-level configs |
| **Example** | "EKS v1.20 EOL in 3 months" | "EKS cluster on v1.19" |

## When to Use What

**Use Health for:**
- Proactive lifecycle notifications
- Planned deprecations
- Service disruptions
- Upgrade windows
- Account-specific events

**Use Config for:**
- Compliance monitoring
- Configuration drift
- Resource auditing
- Current state validation
- Compliance reporting

## Example Scenarios

**Scenario 1:** "Notify when EKS version reaches end of support"
**Answer:** Health (planned lifecycle event)

**Scenario 2:** "Detect clusters running unsupported versions"
**Answer:** Config (configuration compliance)

**Scenario 3:** "Alert on service outage affecting resources"
**Answer:** Health (service event)

**Scenario 4:** "Ensure all S3 buckets encrypted"
**Answer:** Config (compliance rule)

## Integration

**Both can trigger:**
- EventBridge rules
- Lambda functions
- SNS notifications

**Often used together:**
- Health: Warns about upcoming EOL
- Config: Detects non-compliant versions
- Complementary, not exclusive

## Exam Tip

**Keywords:**
- "Lifecycle," "EOL," "deprecation," "planned" → Health
- "Compliance," "configuration," "current state" → Config
- "Notify before" → Health
- "Detect violations" → Config