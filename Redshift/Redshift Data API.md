---
title: Redshift Data API
updated: 2024-11-17 22:54:29Z
created: 2024-11-17 22:52:36Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

Amazon Redshift Data API is an Amazon Redshift feature that simplifies access to your Amazon Redshift data warehouse by removing the need to manage database drivers, connections, network configurations, data buffering, credentials, and more. 

You can run SQL statements using the AWS Software Development Kit (AWS SDK), which supports different languages such as C++, Go, Java, JavaScript, .Net, Node.js, PHP, Python, and Ruby.

With the Data API, you can programmatically access data in your Amazon Redshift cluster from different AWS services such as AWS Lambda, Amazon SageMaker notebooks, and also your on-premises applications using the AWS SDK. 

This allows you to build cloud-native, containerized, serverless, web-based, and event-driven applications on the AWS Cloud.

The Data API also enables you to run analytical queries on Amazon Redshift’s native tables, external tables in your data lake via Amazon Redshift Spectrum, and also across Amazon Redshift clusters, which is known as data sharing. You can also perform federated queries with external data sources like Amazon Aurora.

In the given scenario, the company needs to run SQL queries from applications without managing database connections, which is exactly what the Data API offers. The Data API handles the management of connections and scalability for you, making it an ideal choice for web applications that need to interact with databases.