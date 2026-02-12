# Origin Access Control (OAC)

CloudFront feature to restrict direct access to S3 origins.

## Purpose
Force users to access S3 content only through CloudFront, not directly.


## Benefits
- Prevent bypassing CloudFront
- Protect S3 from direct access
- Enforce caching and security policies
- Reduce S3 costs (CloudFront caching)

**Use:** Standard pattern for CloudFront + S3 private content.