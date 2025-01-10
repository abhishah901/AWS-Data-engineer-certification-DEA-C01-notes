---
title: Job metrics
updated: 2024-11-11 02:30:45Z
created: 2024-11-11 02:30:01Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

AWS Glue provides a feature called job metrics, which can be used to estimate the number of DPUs that can be used to scale out an AWS Glue job. 

This feature is particularly useful in understanding the resource utilization of your jobs and can help in making informed decisions about scaling.

When you run a job, AWS Glue provides metrics such as the total number of actively running executors, the number of completed stages, and the number of maximum needed executors. 

These metrics can give you insights into whether your job is under-provisioned or over-provisioned.