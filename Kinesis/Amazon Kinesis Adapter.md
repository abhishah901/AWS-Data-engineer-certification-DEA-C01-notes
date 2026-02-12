# Amazon Kinesis Adapter

Library that enables applications to consume Kinesis Data Streams using DynamoDB Streams API.

## Purpose
- Migrate DynamoDB Streams applications to Kinesis
- Use existing DynamoDB Streams code with Kinesis
- Minimal code changes required



## Use Case
Reuse DynamoDB Streams processing logic (Lambda, KCL apps) with Kinesis Data Streams without rewriting code.

## Key Point
It's a compatibility layer, not a service. Used for code migration/reuse between DynamoDB Streams and Kinesis Data Streams.