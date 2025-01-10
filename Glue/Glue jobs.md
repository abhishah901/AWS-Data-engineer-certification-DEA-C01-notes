---
title: Glue jobs
updated: 2024-11-09 04:47:48Z
created: 2024-11-09 04:46:13Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

AWS Glue jobs can then be used to process some (crawled) data.

Glue jobs are defined using Python or Scala scripts that reference the schemas and metadata in the AWS Glue Data Catalog. 

This allows Glue jobs to work with changing schemas without needing redeploys as the underlying data changes.

Glue Jobs allow for the transformation and loading of data into Amazon S3 within the required timeframe.