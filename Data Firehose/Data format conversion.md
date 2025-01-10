---
title: Data format conversion
updated: 2024-11-23 21:41:03Z
created: 2024-11-23 21:40:50Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon Data Firehose can convert the format of your input data from JSON to Apache Parquet or Apache ORC before storing the data in Amazon S3. 

Parquet and ORC are columnar data formats that save space and enable faster queries compared to row-oriented formats like JSON. 

If you want to convert an input format other than JSON, such as comma-separated values (CSV) or structured text, you can use AWS Lambda to transform it to JSON first.