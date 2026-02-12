# Commands

## RefreshCache
Forces File Gateway to check S3 for updated objects and refresh local cache.

**When to use:**
- Files modified directly in S3 (bypassing gateway)
- Sync changes made by other gateways
- Before accessing recently updated S3 objects

**Command:**
```bash
aws storagegateway refresh-cache \
  --file-share-arn arn:aws:storagegateway:region:account:share/share-id
```

## Other Key Commands

**NotifyWhenUploaded**
- Get notification when local file uploaded to S3
- Returns notification ID to track upload status

**SetSMBGuestPassword**
- Set password for guest access to SMB file share

**UpdateBandwidthRateLimit**
- Throttle upload/download bandwidth
- Prevent gateway from consuming all network

**UpdateMaintenanceStartTime**
- Schedule maintenance window for updates

**UpdateFileSystemAssociation** (FSx File Gateway)
- Update FSx for Windows File Server association

**ListLocalDisks**
- View available disks for cache/upload buffer

## Common Pattern
Direct S3 modification → RefreshCache → Gateway sees updates