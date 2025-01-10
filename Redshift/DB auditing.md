---
title: DB auditing
updated: 2024-11-09 05:42:43Z
created: 2024-11-09 05:37:11Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon Redshift keeps a record of all connections and user activities in your database, which is commonly known as database auditing. 

These logs are essential for security and troubleshooting purposes. They are stored in Amazon S3 buckets, which provide easy access and data security features for those who monitor database activities.

Amazon Redshift creates three types of log files containing different information:

- **Connection log** – records all authentication attempts, connections, and disconnections.
- **User log** – keeps track of changes to database user definitions.
- **User activity log** – records each query before it is run on the database.

The user activity log is handy for troubleshooting since it provides information about the types of queries the users and the system perform in the database.

You need database permissions to query the system tables, while the log files rely on Amazon S3 permissions. 

Viewing the information in log files instead of querying system tables also helps reduce the impact of interacting with the database.