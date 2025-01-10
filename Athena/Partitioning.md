---
title: Partitioning
updated: 2024-11-09 06:21:31Z
created: 2024-11-09 06:20:56Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Partitioning enables Athena to scan only the relevant partitions of data for a query rather than the entire dataset.

Partitioning can significantly reduce the amount of data scanned, lowering costs.

This method is highly recommended for large datasets stored in S3, where queries often target a subset of the data based on specific columns like date, region, or department.