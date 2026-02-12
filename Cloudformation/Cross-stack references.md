# CloudFormation Cross-Stack References

Share outputs from one stack to another using Exports and Imports.

## How It Works

**Stack A (Export):**
```yaml
Outputs:
  VPCId:
    Value: !Ref MyVPC
    Export:
      Name: MyVPC-ID
```

**Stack B (Import):**
```yaml
Resources:
  MySubnet:
    Type: AWS::EC2::Subnet
    Properties:
      VpcId: !ImportValue MyVPC-ID
```

## Key Rules
- Export names must be unique within region
- Can't delete/update export if another stack imports it
- Must delete importing stack first
- Same region only

## Use Cases
- Shared VPC across multiple application stacks
- Shared load balancer
- Database endpoint sharing
- Network infrastructure separation

## vs Parameters
**Cross-stack references:** Automatic linking, enforced dependencies
**Parameters:** Manual passing, no dependencies

**Best for:** Logical separation of infrastructure (network stack, app stack, database stack).