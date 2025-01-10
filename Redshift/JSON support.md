---
title: JSON support
updated: 2024-11-09 06:25:07Z
created: 2024-11-09 06:23:47Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon Redshift supports querying nested data in JSON columns using dot and bracket notation. This allows you to access and query nested data efficiently, which is especially useful when dealing with large datasets.

 For example, if you have a JSON column data with nested fields `field1` and `field2`, you can access the nested data using the following syntax: `data.field1` or `data["field1"]`. This approach provides the least operational overhead, making it the most suitable for the given task. 
 
 It allows you to access the required data directly without having to process the entire JSON object, thereby reducing the computational resources required for the query.