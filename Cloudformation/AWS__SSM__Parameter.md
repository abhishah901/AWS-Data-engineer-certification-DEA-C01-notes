# AWS::SSM::Parameter

CloudFormation resource to create Systems Manager Parameter Store parameters.

## Syntax
```yaml
MyParameter:
  Type: AWS::SSM::Parameter
  Properties:
    Name: /myapp/config/dbhost
    Type: String              # String, StringList, SecureString
    Value: db.example.com
    Description: Database hostname
    Tier: Standard            # Standard or Advanced
    DataType: text            # text, aws:ec2:image, aws:ssm:integration
```

## Parameter Types
- **String:** Plain text
- **StringList:** Comma-separated values
- **SecureString:** Encrypted with KMS

## Example - SecureString
```yaml
DBPassword:
  Type: AWS::SSM::Parameter
  Properties:
    Name: /myapp/db/password
    Type: SecureString
    Value: !Ref DatabasePassword
    KmsKeyId: alias/aws/ssm
```

## Use Cases
- Store configuration values
- Share parameters across stacks
- Reference in EC2 user data
- Dynamic references in CloudFormation

## Reference Parameter
```yaml
# In another template
InstanceUserData:
  Fn::Base64: !Sub |
    #!/bin/bash
    DB_HOST=$(aws ssm get-parameter --name /myapp/config/dbhost --query Parameter.Value)
```

**vs CloudFormation Parameters:** SSM stored centrally, reusable across stacks. CFN parameters passed at deploy time.