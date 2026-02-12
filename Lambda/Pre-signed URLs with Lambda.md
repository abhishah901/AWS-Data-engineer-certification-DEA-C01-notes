# Pre-signed URLs with Lambda

## What They Are
Temporary URLs granting time-limited access to private S3 objects without making them public.

## Lambda Use Cases

**Generate pre-signed URL:**
```python
import boto3
from botocore.exceptions import ClientError

def lambda_handler(event, context):
    s3_client = boto3.client('s3')
    
    try:
        url = s3_client.generate_presigned_url(
            'get_object',
            Params={
                'Bucket': 'my-bucket',
                'Key': 'private/file.pdf'
            },
            ExpiresIn=3600  # 1 hour
        )
        return {'statusCode': 200, 'body': url}
    except ClientError as e:
        return {'statusCode': 500, 'body': str(e)}
```

**Upload pre-signed URL:**
```python
url = s3_client.generate_presigned_url(
    'put_object',
    Params={'Bucket': 'my-bucket', 'Key': 'uploads/file.jpg'},
    ExpiresIn=3600
)
```

## Common Pattern
API Gateway → Lambda → Generate pre-signed URL → Return to client → Client uploads/downloads directly to/from S3

## Benefits
- **No Lambda data transfer (client talks directly to S3)**
- Reduced Lambda execution time
- Cost-effective for large files
- Temporary access without IAM credentials

## IAM Permissions
Lambda execution role needs `s3:GetObject` (for downloads) or `s3:PutObject` (for uploads).