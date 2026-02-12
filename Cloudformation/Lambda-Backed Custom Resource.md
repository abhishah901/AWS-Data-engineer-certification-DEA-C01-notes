# Lambda-Backed Custom Resource

CloudFormation custom resource using Lambda to perform actions CloudFormation doesn't natively support.

## Purpose
Extend CloudFormation with custom logic (API calls, third-party integrations, cleanup tasks).

## Template Syntax
```yaml
Resources:
  MyCustomResource:
    Type: Custom::MyResourceType
    Properties:
      ServiceToken: !GetAtt MyLambdaFunction.Arn
      CustomProperty1: value1
      CustomProperty2: value2
  
  MyLambdaFunction:
    Type: AWS::Lambda::Function
    Properties:
      Handler: index.handler
      Runtime: python3.9
      Role: !GetAtt LambdaRole.Arn
      Code:
        ZipFile: |
          import cfnresponse
          def handler(event, context):
              # Custom logic here
              cfnresponse.send(event, context, cfnresponse.SUCCESS, {})
```

## Lambda Handler
```python
import cfnresponse
import boto3

def handler(event, context):
    request_type = event['RequestType']  # Create, Update, Delete
    properties = event['ResourceProperties']
    
    try:
        if request_type == 'Create':
            # Create resource logic
            result = create_resource(properties)
            response_data = {'ResourceId': result['id']}
            cfnresponse.send(event, context, cfnresponse.SUCCESS, response_data)
        
        elif request_type == 'Update':
            # Update resource logic
            update_resource(properties)
            cfnresponse.send(event, context, cfnresponse.SUCCESS, {})
        
        elif request_type == 'Delete':
            # Delete resource logic
            delete_resource(properties)
            cfnresponse.send(event, context, cfnresponse.SUCCESS, {})
    
    except Exception as e:
        cfnresponse.send(event, context, cfnresponse.FAILED, {})
```

## Common Use Cases

- Empty S3 bucket before deletion
- Populate DynamoDB with initial data
- Call external APIs
- Certificate validation
- SNS subscription confirmation
- Custom resource provisioning

## CRITICAL: Response Required

**Must call `cfnresponse.send()` or stack hangs!**

Timeout = 1 hour, then CREATE_FAILED/DELETE_FAILED.

## Return Values
```python
response_data = {
    'Key1': 'value1',
    'Key2': 'value2'
}
cfnresponse.send(event, context, cfnresponse.SUCCESS, response_data)
```

**Reference in template:**
```yaml
Outputs:
  CustomValue:
    Value: !GetAtt MyCustomResource.Key1
```

**Use:** Extend CloudFormation for unsupported operations.