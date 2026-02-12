# RefreshCache API - Storage Gateway

## What It Does
Synchronizes file gateway cache with S3 bucket when files added directly to S3 (bypassing gateway)

## API Call
aws storagegateway refresh-cache --file-share-arn arn:aws:... --folder-list "/"

## When to Use
- Files uploaded directly to S3 (not through gateway)
- Gateway doesn't see new S3 objects
- Need to update gateway's view of bucket

## How It Works
Problem: File gateway caches metadata, doesn't see direct S3 uploads
Solution: RefreshCache forces gateway to scan S3 and update cache

## Common Pattern
S3 upload → Lambda → RefreshCache API → Gateway sees file

## When NOT Needed
Files written through gateway (automatic cache update)

## Key Points
- Async operation (not instant)
- On-demand refresh vs automatic periodic
- Only for external S3 changes