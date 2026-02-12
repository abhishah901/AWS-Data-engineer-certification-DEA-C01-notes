# CloudFormation Nested Stacks

Stacks that create other stacks as resources - reusable components.

## Purpose
Break large template into smaller, reusable pieces.

## How It Works
```
Parent Stack
├── Network Stack (VPC, subnets)
├── Security Stack (IAM, SGs)
└── App Stack (EC2, RDS)
```

## Syntax
```yaml
Resources:
  NetworkStack:
    Type: AWS::CloudFormation::Stack
    Properties:
      TemplateURL: https://s3.amazonaws.com/bucket/network.yaml
      Parameters:
        VPCCidr: 10.0.0.0/16
  
  AppStack:
    Type: AWS::CloudFormation::Stack
    DependsOn: NetworkStack
    Properties:
      TemplateURL: https://s3.amazonaws.com/bucket/app.yaml
      Parameters:
        VPCId: !GetAtt NetworkStack.Outputs.VPCId
```

## Key Points
- Templates stored in S3
- Parent passes parameters to child
- Child returns outputs
- Update parent → updates all nested stacks
- Delete parent → deletes all nested stacks

## vs StackSets
**Nested:** Organize single deployment (components)
**StackSets:** Deploy same stack to multiple accounts/regions

**Use:** Reusable components, organize complex infrastructure, share templates across projects.