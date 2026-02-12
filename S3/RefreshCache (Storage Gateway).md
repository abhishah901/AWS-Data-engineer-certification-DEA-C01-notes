# RefreshCache (Storage Gateway)

Forces File Gateway to check S3 for updated objects and refresh local cache.

## When to Use
- Files modified directly in S3 (bypassing gateway)
- Sync changes from other gateways
- Before accessing recently updated S3 objects

## Command
```bash
aws storagegateway refresh-cache \
  --file-share-arn arn:aws:storagegateway:region:account:share/share-id
```

## Use Case
Direct S3 modification → RefreshCache → Gateway sees updates

**Why needed:** File Gateway caches locally - doesn't automatically detect S3 changes made outside gateway.