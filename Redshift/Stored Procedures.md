---
title: Stored Procedures
updated: 2024-11-13 03:46:20Z
created: 2024-11-11 02:06:24Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

In Amazon Redshift, stored procedures serve as a mechanism to encapsulate logic for various operations, such as data transformation and validation, as well as business-specific logic. 

This encapsulation allows for a more streamlined and efficient process, particularly when dealing with multiple SQL statements. By bundling these statements into a single stored procedure, the number of round trips between the custom-built application and the database can be significantly reduced, thereby simplifying the operation and enhancing network traffic efficiency.



Stored procedures are stored directly in the database, making them accessible to any user with the appropriate privileges. 

They offer a level of flexibility not found in user-defined functions ([User Defined Functions](../../../Certi/AWS%20Data%20Engineering/Redshift/User%20Defined%20Functions.md)), as they can incorporate not only SELECT queries but also data definition language (DDL) and data manipulation language (DML). Unlike UDFs, stored procedures do not necessarily need to return a value.


Stored procedures in Amazon Redshift are used to encapsulate logic for data transformation, data validation, and business-specific logic. 

By combining multiple SQL steps into a stored procedure, you can reduce round trips between your custom-built application and the database. 

This would simplify the operation and improve the network traffic between the custom-built application and Redshift.


`EXECUTE` permission allows users to run a stored procedure. This is the main permission required to allow users to execute procedures. `GRANT EXECUTE` is used to provide this permission.

`INSERT`, `UPDATE`, and `DELETE` permissions on underlying tables or views allow read/write access.

`USAGE` permission on schemas is required to allow creating and managing procedures within that schema.

`ALTER` permission on the procedure allows modifying the procedure definition after creation.

`REFERENCES` permission allows using the procedure name in SQL statements like CALL.