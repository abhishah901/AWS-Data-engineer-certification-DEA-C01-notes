---
title: Materialized Views
updated: 2024-11-15 03:56:17Z
created: 2024-11-15 03:27:09Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Materialized views in Amazon Redshift provide a way to handle complex queries on large datasets. A materialized view contains a precomputed result set, based on an SQL query over one or more base tables. 

This means that the results of the query are calculated and stored when the view is created, rather than being calculated at query time. This can significantly speed up query performance on large datasets.

Materialized views are especially useful for speeding up queries that are predictable and repeated. Instead of performing resource-intensive queries against large tables (such as aggregates or multiple joins), applications can query a materialized view and retrieve a precomputed result set. 

For example, consider the scenario where a set of queries is used to populate dashboards, such as Amazon QuickSight. This use case is ideal for a materialized view, because the queries are predictable and repeated over and over again.