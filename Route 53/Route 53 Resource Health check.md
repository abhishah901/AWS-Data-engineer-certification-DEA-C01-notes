Route 53 can check the health of your resources in both simple and complex
conﬁgurations:

- In simple conﬁgurations, you create a group of records that all have the same
name and type, such as a group of weighted records with a type of A. You then conﬁgure Route 53 to check the health of the
corresponding resources. Route 53 responds to DNS queries based on the health
of your resources.

- In more complex conﬁgurations, you create a tree of records that route traﬃc
based on multiple criteria. For example, if latency for your users is your most
important criterion, then you might use latency alias records to route traﬃc to
the region that provides the best latency. The latency alias records might have
weighted records in each region as the alias target. The weighted records might
route traﬃc to EC2 instances based on the instance type. As with a simple
conﬁguration, you can conﬁgure Route 53 to route traﬃc based on the health of
your resources.