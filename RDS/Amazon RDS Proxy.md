# Amazon RDS Proxy

Fully managed database proxy for RDS and Aurora.

## Purpose
Pool and share database connections to improve scalability and availability.

## Key Features

**Connection Pooling:**
- Reduces DB connection overhead
- Handles thousands of app connections with fewer DB connections

**Failover:**
- 66% faster RDS/Aurora failover
- Preserves connections during failover
- Apps don't need to re-establish connections

**Security:**
- IAM authentication
- Secrets Manager integration
- No credential management in app code

**Serverless-Friendly:**
- Perfect for Lambda (connection reuse)
- Eliminates "too many connections" errors

## How It Works
```
Lambda/App → RDS Proxy (connection pool) → RDS/Aurora
```

## Use Cases
- Lambda functions accessing RDS
- Apps with many short-lived connections
- Improve failover time
- Reduce database connection overhead
- IAM-based DB authentication

## Supported Databases
MySQL, PostgreSQL, MariaDB, SQL Server

## Pricing
Per vCPU-hour + data processed

**Common pattern:** Lambda + RDS Proxy = efficient, scalable database access.