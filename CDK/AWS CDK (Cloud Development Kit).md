# AWS CDK (Cloud Development Kit)

Define AWS infrastructure using programming languages instead of JSON/YAML.

## Supported Languages
- TypeScript, JavaScript
- Python
- Java
- C#/.NET
- Go

## Key Concepts

**Constructs:**
- Building blocks (L1, L2, L3)
- L1: Direct CloudFormation resources
- L2: Higher-level with defaults
- L3: Patterns (complete architectures)

**Stacks:**
- Deployment unit (becomes CloudFormation stack)

**Apps:**
- Collection of stacks

## Example (Python)
```python
from aws_cdk import Stack, aws_s3 as s3
from constructs import Construct

class MyStack(Stack):
    def __init__(self, scope: Construct, id: str):
        super().__init__(scope, id)
        
        bucket = s3.Bucket(self, "MyBucket",
            versioned=True,
            encryption=s3.BucketEncryption.S3_MANAGED
        )
```

## Workflow
```
Write code → cdk synth → CloudFormation template → cdk deploy → AWS resources
```

## vs CloudFormation
- **CDK:** Code (loops, conditionals, IDE support)
- **CFN:** Declarative templates (JSON/YAML)

## vs Terraform
- **CDK:** AWS-native, generates CloudFormation
- **Terraform:** Multi-cloud, own state management

**Use:** Prefer coding over templates, reusable components, type safety.