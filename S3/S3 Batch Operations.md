# S3 Batch Operations

Perform large-scale operations on billions of S3 objects.

## Purpose
Execute actions on massive numbers of objects (millions/billions) in a single job.

## Supported Operations

**Object management:**
- Copy objects
- Invoke Lambda function
- Restore from Glacier
- Replace object tags
- Delete object tags
- Replace ACLs
- Object Lock retention
- Legal hold

## How It Works

1. Create manifest (list of objects to process)
2. Create batch job with operation
3. Job runs asynchronously
4. Get completion report

## Manifest Sources

- S3 Inventory report (CSV)
- Manual CSV file
- S3 Select query results

**Manifest format:**
```
bucket,key
my-bucket,file1.txt
my-bucket,file2.txt
```

## Use Cases

**Good for:**
- Copy millions of objects between buckets
- Restore large Glacier archives
- Tag 100 million objects
- Update ACLs on entire buckets
- Encrypt unencrypted objects at scale

**NOT good for:**
- Individual object operations
- Real-time event responses
- Small-scale tasks (< 1000 objects)

## vs Regular S3 Operations

**Batch Operations:**
- Millions/billions of objects
- Manifest-based
- Async job
- Progress tracking

**Regular API:**
- Individual objects
- Event-driven
- Immediate
- No job tracking

## Pricing

- Per object processed
- Manifest creation (if using Inventory)
- Storage for reports

## Job Completion Report

Shows:
- Objects processed
- Success/failure count
- Failed objects list
- Error reasons

## When to Use

**Batch Operations:** "Copy 10 million objects" "Tag all untagged objects in bucket"
**Event-driven Lambda:** "Copy this object when uploaded" "Process image on upload"

## Exam Context

Often presented as wrong answer for:
- Real-time event processing
- Individual object operations
- Automatic retry mechanisms

**Key signal:** "Large-scale" or "millions of objects" = Batch Operations