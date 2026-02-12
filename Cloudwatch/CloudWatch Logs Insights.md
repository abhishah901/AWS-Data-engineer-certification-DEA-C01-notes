# CloudWatch Logs Insights

Interactive log analytics service for querying CloudWatch Logs.

## Purpose
Query and analyze log data using SQL-like syntax.

## Key Features
- Purpose-built query language
- Automatic field discovery
- Visual results (time series, bar charts)
- Save queries for reuse
- Pay per query (GB scanned)

## Query Examples

**Find errors:**
```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 20
```

**Aggregate by status code:**
```
fields @timestamp, status
| stats count() by status
```

**P99 latency:**
```
fields @timestamp, duration
| stats avg(duration), max(duration), pct(duration, 99)
```

**Parse JSON logs:**
```
fields @timestamp, requestId, @message
| parse @message '"statusCode":*,' as statusCode
| filter statusCode = 500
```

## Use Cases
- Troubleshoot application issues
- Analyze trends
- Security analysis
- Performance monitoring

## vs Other Tools
- **Athena:** Complex SQL on exported logs (S3)
- **Insights:** Quick interactive queries on live logs
- **OpenSearch:** Full-text search, dashboards

**Best for:** Ad-hoc log analysis without infrastructure setup.