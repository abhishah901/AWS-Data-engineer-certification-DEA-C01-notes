---
title: Data migration tasks (with CDC)
updated: 2024-11-09 05:33:14Z
created: 2024-11-09 05:28:46Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

An AWS DMS task can be created to capture ongoing changes from the source data store during the data migration process.

The source or target of the migration must be on AWS.

Additionally, a task can be configured to capture ongoing changes after completing the initial full-load migration to a supported target data store. This process, known as ongoing replication or change data capture (CDC), is employed by AWS DMS when replicating ongoing changes from a source data store. The CDC process works by collecting changes to the database logs using the database engine’s native API.

- Full load plus Change data capture (CDC) – The task migrates existing data and then updates the target database based on changes to the source database.
- Change data capture (CDC) only – The task migrates ongoing changes after you have data on your target database.



With Microsoft SQL Server as the source, full transaction logging must be turned on to enable CDC. 

If the source is a MySQL database, binary logging must be enabled first before CDC can be utilized.