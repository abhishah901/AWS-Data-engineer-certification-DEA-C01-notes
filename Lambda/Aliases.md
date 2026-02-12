# Lambda Aliases

Pointer to specific Lambda function version.

## What They Are
- Named reference (e.g., "prod", "dev", "blue")
- Points to one or more versions
- Has own ARN
- Mutable (can change which version it points to)

## Key Features

**Version Routing (Traffic Shifting)**
```
Alias "prod" →
  - 90% traffic to version 5
  - 10% traffic to version 6
```

**Use Cases:**
- Blue/green deployments
- Canary testing
- Rollbacks (point to previous version)
- Environment management (dev/test/prod)

## Example
```bash
# Create alias
aws lambda create-alias \
  --function-name myFunction \
  --name prod \
  --function-version 3

# Update alias to new version
aws lambda update-alias \
  --function-name myFunction \
  --name prod \
  --function-version 4 \
  --routing-config AdditionalVersionWeights={"3"=0.1}
```

## Versions vs Aliases

| Feature | Version | Alias |
|---------|---------|-------|
| Mutability | Immutable | Mutable |
| ARN | Unique | Unique |
| Traffic split | No | Yes |
| Use | Fixed snapshot | Flexible pointer |

## Common Pattern
$LATEST → Version 5 → Alias "prod" → API Gateway/EventBridge

**Benefits:** Change versions without updating all consumers.