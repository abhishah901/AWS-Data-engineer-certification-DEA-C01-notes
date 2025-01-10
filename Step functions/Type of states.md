---
title: Type of states
updated: 2024-11-13 04:56:11Z
created: 2024-11-13 04:51:57Z
latitude: 32.73568700
longitude: -97.10806560
altitude: 0.0000
---

A `Parallel` state causes AWS Step Functions to execute each branch, starting with the state named in that branch’s StartAt field, as concurrently as possible and wait until all branches terminate (reach a terminal state) before processing the Parallel state’s Next field.

The `Fail` state in AWS Step Functions is used to terminate the state machine with a failure. 

The `Choice` state simply allows for branching logic based on input data.

`Success` is just used to terminate the execution of a state machine successfully. 