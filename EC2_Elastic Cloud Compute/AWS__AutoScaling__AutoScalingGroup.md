```
MyASG:
  Type: AWS::AutoScaling::AutoScalingGroup
  Properties:
    MinSize: 1
    MaxSize: 10
    DesiredCapacity: 3
    VPCZoneIdentifier:
      - subnet-abc123
      - subnet-def456
    LaunchTemplate:
      LaunchTemplateId: !Ref MyLaunchTemplate
      Version: !GetAtt MyLaunchTemplate.LatestVersionNumber
```

## Key Properties Reference

| Property | Type | Description |
|----------|------|-------------|
| MinSize | Integer | Minimum capacity (required) |
| MaxSize | Integer | Maximum capacity (required) |
| DesiredCapacity | Integer | Target capacity (optional) |
| VPCZoneIdentifier | List | Subnet IDs |
| TargetGroupARNs | List | ALB/NLB target groups |
| HealthCheckType | String | EC2 or ELB |
| HealthCheckGracePeriod | Integer | Wait before health checks (seconds) |
| DefaultInstanceWarmup | Integer | Wait before metrics/scaling |
| Cooldown | Integer | Wait between scaling activities |


## Update Policies
```yaml
# Rolling Update
UpdatePolicy:
  AutoScalingRollingUpdate:
    MinInstancesInService: Integer
    MaxBatchSize: Integer
    PauseTime: String  # PT5M = 5 min
    WaitOnResourceSignals: Boolean
    SuspendProcesses:
      - HealthCheck
      - ReplaceUnhealthy

# Replacing Update
UpdatePolicy:
  AutoScalingReplacingUpdate:
    WillReplace: true

# Scheduled Action
UpdatePolicy:
  AutoScalingScheduledAction:
    IgnoreUnmodifiedGroupSizeProperties: Boolean
```


