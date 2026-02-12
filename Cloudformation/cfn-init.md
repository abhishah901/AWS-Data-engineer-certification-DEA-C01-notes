# cfn-init

CloudFormation helper script that retrieves and interprets metadata from CloudFormation templates.

## Purpose
Configure EC2 instances during stack creation using declarative syntax instead of bash scripts.

## How It Works
1. Define metadata in template (`AWS::CloudFormation::Init`)
2. Run `cfn-init` in UserData
3. Script reads metadata and applies configuration

## Example

**Template Metadata:**
```yaml
Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Metadata:
      AWS::CloudFormation::Init:
        config:
          packages:
            yum:
              httpd: []
          files:
            /var/www/html/index.html:
              content: "Hello World"
          services:
            sysvinit:
              httpd:
                enabled: true
                ensureRunning: true
    Properties:
      UserData:
        Fn::Base64: !Sub |
          #!/bin/bash
          yum update -y aws-cfn-bootstrap
          /opt/aws/bin/cfn-init -v \
            --stack ${AWS::StackName} \
            --resource MyInstance \
            --region ${AWS::Region}
```

## Capabilities
- Install packages (yum, apt, rpm)
- Create files
- Run commands
- Start services
- Create users/groups

## Related Scripts
- **cfn-init:** Apply configuration
- **cfn-signal:** Signal success/failure to CloudFormation
- **cfn-hup:** Detect metadata changes and reapply
- **cfn-get-metadata:** Retrieve metadata

**vs UserData alone:** cfn-init is declarative, organized, easier to maintain than long bash scripts.