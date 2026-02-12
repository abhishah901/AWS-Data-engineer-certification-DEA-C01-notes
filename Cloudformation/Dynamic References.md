# Dynamic References

Retrieve external values in CloudFormation templates at runtime.

## Types

**SSM Parameters:**
```yaml
MyParameter: '{{resolve:ssm:/myapp/db/password:1}}'
# Retrieves version 1 of SSM parameter
```

**SSM Secure Strings:**
```yaml
MySecret: '{{resolve:ssm-secure:/myapp/api-key:1}}'
# Retrieves encrypted SSM parameter
```

**Secrets Manager:**
```yaml
MySecret: '{{resolve:secretsmanager:MySecret:SecretString:password}}'
# Retrieves specific key from secret
```

## Benefits
- No hardcoded secrets in templates
- Values resolved at stack creation/update
- Automatic secret rotation support
- Cross-account/region references

## Example
```yaml
Resources:
  MyDB:
    Type: AWS::RDS::DBInstance
    Properties:
      MasterUsername: admin
      MasterUserPassword: '{{resolve:secretsmanager:prod/db/master:SecretString:password}}'
```

## vs Parameters
**CloudFormation Parameters:** User provides at deploy time
**Dynamic References:** Auto-fetched from SSM/Secrets Manager

**Use:** Store secrets centrally, reference in multiple stacks without duplication.