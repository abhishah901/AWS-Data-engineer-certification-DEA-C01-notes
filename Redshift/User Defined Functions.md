---
title: User Defined Functions
updated: 2024-11-09 03:44:37Z
created: 2024-11-09 03:28:27Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Create custom scalar UDFs using either a SQL SELECT clause or a Python program. 

Once created, the UDF is stored in the database and is available for any user with sufficient privileges to run.

Running a custom scalar UDF in Amazon Redshift is as straightforward as running existing Amazon Redshift functions. This means you don’t need to learn new ways of invoking functions, saving you time and effort.

UDFs in Redshift provide more control and flexibility over data processing workflows and potentially improve performance by reducing the amount of data transferred between the database and client application. This is because the computations are done within the database itself, rather than transferring data to an external location for processing.