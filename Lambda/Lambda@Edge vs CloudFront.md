# Lambda@Edge vs CloudFront

## CloudFront
CDN service that caches and delivers content globally.

**Features:**
- Content caching at edge locations
- Static/dynamic content delivery
- HTTPS/HTTP support
- Custom SSL certificates
- Origin failover
- Field-level encryption

**Use:** Content delivery, reduce latency, offload origin

## Lambda@Edge
Run Lambda functions at CloudFront edge locations.

**Triggers:**
- Viewer Request (before cache check)
- Origin Request (cache miss, before origin)
- Origin Response (after origin, before cache)
- Viewer Response (before returning to user)

**Use Cases:**
- A/B testing (modify requests)
- URL rewrites/redirects
- Auth at edge (check tokens)
- Header manipulation
- Image resizing on-the-fly
- Bot detection

## Relationship
Lambda@Edge **extends** CloudFront with custom logic at the edge. CloudFront is the CDN, Lambda@Edge adds programmability.

## Example
```javascript
// Lambda@Edge function
exports.handler = async (event) => {
    const request = event.Records[0].cf.request;
    
    // Redirect mobile users
    if (request.headers['user-agent'][0].value.includes('Mobile')) {
        request.uri = '/mobile' + request.uri;
    }
    
    return request;
};
```

## Key Difference
- **CloudFront alone:** Static rules, caching, delivery
- **CloudFront + Lambda@Edge:** Dynamic logic at edge