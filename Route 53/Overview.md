# Route 53

AWS DNS web service.

## Core Functions
- Domain registration
- DNS routing
- Health checking
- Traffic management

## Routing Policies

**Simple**
- Single resource, no health checks
- Use: Basic DNS

**Weighted**
- Split traffic by percentages (70/30)
- Use: A/B testing, gradual migration

**Latency**
- Route to lowest latency endpoint
- Use: Global apps, performance optimization

**Failover**
- Primary/secondary with health checks
- Use: Active-passive DR

**Geolocation**
- Route based on user location
- Use: Content localization, compliance

**Geoproximity**
- Route based on resource/user location with bias
- Use: Fine-tuned geographic routing

**Multi-value**
- Return multiple IPs with health checks
- Use: Simple load distribution

## Health Checks
- Monitor endpoint status
- HTTP/HTTPS/TCP checks
- Can trigger CloudWatch alarms
- Required for failover routing

## Key Features
- 100% SLA
- Global service (not regional)
- Integrates with ELB, CloudFront, S3
- Private hosted zones for VPC

## Common Patterns
- Multi-region failover
- Blue/green deployments (weighted routing)
- DR with health checks