# CDK vs SAM

## AWS CDK
**Infrastructure as Code using programming languages**

- Full AWS infrastructure (any resource)
- TypeScript, Python, Java, C#, Go
- Generates CloudFormation templates
- Reusable constructs/patterns
- Best for: Complex infrastructure, multi-service apps

## AWS SAM (Serverless Application Model)
**Simplified framework for serverless apps**

- Serverless-focused (Lambda, API Gateway, DynamoDB, etc.)
- YAML/JSON templates (extension of CloudFormation)
- Local testing (`sam local`)
- Quick serverless deployments
- Best for: Serverless applications

## Key Differences

| Feature | CDK | SAM |
|---------|-----|-----|
| Scope | All AWS resources | Serverless resources |
| Language | Programming languages | YAML/JSON |
| Learning curve | Higher | Lower |
| Local testing | Limited | Built-in |
| Flexibility | Maximum | Serverless-focused |

## Example

**CDK:**
```python
lambda_fn = lambda_.Function(self, "Handler",
    runtime=lambda_.Runtime.PYTHON_3_9,
    code=lambda_.Code.from_asset("lambda"),
    handler="index.handler"
)
```

**SAM:**
```yaml
Resources:
  MyFunction:
    Type: AWS::Serverless::Function
    Properties:
      Runtime: python3.9
      CodeUri: lambda/
      Handler: index.handler
```

## Decision
- **SAM:** Quick serverless apps, local testing, simpler
- **CDK:** Complex infrastructure, prefer coding, reusable components