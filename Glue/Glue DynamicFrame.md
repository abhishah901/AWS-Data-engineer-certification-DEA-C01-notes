---
title: Glue DynamicFrame
updated: 2024-11-09 04:50:36Z
created: 2024-11-09 04:48:43Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

AWS Glue’s support for server-side filtering with catalog partition predicates directly during the creation of DynamicFrames is a powerful feature for optimizing ETL processes.

This capability allows the ETL job to selectively process only the necessary data by utilizing the metadata catalog’s partition indexes.

Doing so significantly reduces the volume of data that needs to be read and processed, leading to reductions in execution time and cost.