---
title: Glue DataBrew
updated: 2024-12-09 02:21:41Z
created: 2024-12-06 04:10:14Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

- DataBrew >> Visual data preparation tool that simplifies the process of cleaning and normalizing data


AWS Glue DataBrew offers a streamlined solution for data quality management, particularly beneficial in scenarios requiring precise and automated data validation. 

Its ability to define specific data quality rules within a ruleset makes it an optimal choice for scenarios like ensuring inventory data accuracy. 

- serverless


A DataBrew recipe is a set of data transformation steps that are applied sequentially to clean, normalize, and prepare data. Here are some of those recipe steps:

NEST_TO_ARRAY converts selected columns into an array while maintaining their order and typecasting them into a common data type.

NEST_TO_MAP converts user-selected columns into key-value pairs, with each key representing the column name and the corresponding row value as the value. Column order is not preserved, and different column data types are typecast to a common type.

UNNEST_MAP separates a map column into key-value pairs, generating a row for each pair. It only works for one map column level.

UNNEST_ARRAY function extracts array elements into separate rows, allowing only one level of an array column to be unnested.