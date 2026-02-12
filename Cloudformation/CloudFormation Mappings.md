# CloudFormation Mappings

Key-value lookup tables in CloudFormation templates.

## Purpose
Define conditional values based on parameters or pseudo-parameters.

## Syntax
```yaml
Mappings:
  RegionMap:
    us-east-1:
      AMI: ami-0c55b159cbfafe1f0
    eu-west-1:
      AMI: ami-047bb4163c506cd98
    ap-southeast-1:
      AMI: ami-0d058fe428540cd89
  
  EnvironmentMap:
    dev:
      InstanceType: t3.micro
    prod:
      InstanceType: t3.large
```

## Usage - FindInMap
```yaml
Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: !FindInMap [RegionMap, !Ref "AWS::Region", AMI]
      InstanceType: !FindInMap [EnvironmentMap, !Ref Environment, InstanceType]
```

## Common Use Cases
- Region-specific AMI IDs
- Environment-specific instance sizes
- Account-specific configurations
- Multi-tier architectures

## vs Parameters
**Mappings:** Static lookup (defined in template)
**Parameters:** Dynamic input (provided at deploy)

**Best for:** Values that vary by region/environment but are known and fixed.