# GetAtt vs ImportValue

## GetAtt
**Get attribute from resource in SAME stack**

**Syntax:**
```yaml
!GetAtt ResourceName.AttributeName
```

**Scope:** Same stack only

**Example:**
```yaml
Resources:
  MyBucket:
    Type: AWS::S3::Bucket
  
  MyRole:
    Type: AWS::IAM::Role
    Properties:
      Policies:
        - PolicyDocument:
            Statement:
              - Resource: !GetAtt MyBucket.Arn  # Same stack
```

**Common attributes:**
- EC2: PublicIp, PrivateIp
- S3: Arn, DomainName
- Lambda: Arn
- ASG: TargetGroupARNs

## ImportValue
**Import exported value from DIFFERENT stack**

**Syntax:**
```yaml
!ImportValue ExportName
```

**Scope:** Cross-stack

**Example:**

**Stack A (exports):**
```yaml
Outputs:
  VPCId:
    Value: !Ref MyVPC
    Export:
      Name: SharedVPC
```

**Stack B (imports):**
```yaml
Resources:
  MySubnet:
    Type: AWS::EC2::Subnet
    Properties:
      VpcId: !ImportValue SharedVPC  # Different stack
```

## Key Differences

| Feature | GetAtt | ImportValue |
|---------|--------|-------------|
| **Scope** | Same stack | Cross-stack |
| **Requires** | Resource in stack | Export from other stack |
| **Usage** | Get resource attributes | Get exported values |
| **Region** | N/A | Same region only |

## When to Use

**GetAtt:**
- Resource exists in your template
- Need resource attribute (ARN, ID, etc.)

**ImportValue:**
- Resource in different stack
- Another team/stack exports value
- Shared infrastructure

## Cannot Mix

**Wrong:**
```yaml
# Can't GetAtt from other stack
VpcId: !GetAtt OtherStack.VPC  # ❌ Error
```

**Correct:**
```yaml
# Other stack exports, you import
VpcId: !ImportValue OtherStack-VPC  # ✓
```

**Memory trick:**
- **GetAtt** = Get **Attribute** (same stack)
- **ImportValue** = Import **Export** (cross-stack)