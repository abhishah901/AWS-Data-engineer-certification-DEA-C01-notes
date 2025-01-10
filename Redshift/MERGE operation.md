---
title: MERGE operation
updated: 2024-11-12 23:52:00Z
created: 2024-11-12 23:50:42Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

One of the features of Amazon Redshift is the support for the MERGE operation, which uses a temporary staging table. 

This operation is particularly useful when you have a large batch of updated data that often contains updates to existing records, and you want to ensure that the data in Redshift is always up-to-date while minimizing the impact on query performance.

The MERGE operation works by comparing the records in two tables based on a specified match condition. 

When the MERGE operation detects a match between the records in the two tables, it performs an UPDATE operation. This means that the existing records in the main table are updated with the values from the matching records in the temporary table.

On the other hand, when the MERGE operation does not detect a match, it performs an INSERT operation. This means that the new records from the temporary table are inserted into the main table.