# Amazon CloudFront

Global CDN (Content Delivery Network) for fast content delivery.

## Core Function
Cache and deliver content from edge locations closest to users.

## Key Features
- 450+ edge locations globally
- HTTPS/HTTP support
- Custom SSL certificates
- Origin failover
- Lambda@Edge integration
- Real-time metrics

## Origins
- S3 buckets
- ALB/NLB
- EC2 instances
- Custom HTTP servers
- MediaStore/MediaPackage

## Cache Behavior
- Cache based on: path patterns, headers, cookies, query strings
- TTL (Time to Live) controls cache duration
- Invalidations for cache clearing

## Security
- Origin Access Control (OAC) - restrict S3 access
- WAF integration
- Signed URLs/cookies - restrict content access
- DDoS protection (Shield)
- Field-level encryption

## Use Cases
- Static website hosting (S3 + CloudFront)
- Video streaming
- API acceleration
- Software distribution
- Dynamic content delivery

## Pricing
- Data transfer out
- HTTP/HTTPS requests
- Invalidation requests (first 1000/month free)

## Common Pattern
Users → CloudFront (edge cache) → Origin (S3/ALB)