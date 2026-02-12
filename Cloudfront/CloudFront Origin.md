# CloudFront Origin

Source location where CloudFront retrieves content to cache and serve.

## Origin Types

**S3 Bucket:**
- Static content (images, videos, files)
- Use with OAC for security

**Custom Origin (HTTP/HTTPS):**
- ALB/NLB
- EC2 instances
- On-premises servers
- Any HTTP endpoint

**MediaStore/MediaPackage:**
- Video streaming origins

## Multiple Origins
Single distribution can have multiple origins with path-based routing.

**Example:**
```
/images/* → S3 bucket
/api/* → ALB
/* → EC2 instance
```

## Origin Settings

**Origin Protocol:**
- HTTP only
- HTTPS only
- Match viewer

**Origin Path:**
- Prefix for requests (e.g., `/production`)

**Custom Headers:**
- Add headers to origin requests

**Origin Shield:**
- Additional caching layer
- Reduce load on origin

## Origin Failover
Configure primary + secondary origin for HA.

**Decision:** S3 for static, ALB/custom for dynamic content.