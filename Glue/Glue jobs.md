AWS Glue jobs can then be used to process some (crawled) data.

Glue jobs are defined using Python or Scala scripts that reference the schemas and metadata in the AWS Glue Data Catalog. 

This allows Glue jobs to work with changing schemas without needing redeploys as the underlying data changes.

Glue Jobs allow for the transformation and loading of data into Amazon S3 within the required timeframe.