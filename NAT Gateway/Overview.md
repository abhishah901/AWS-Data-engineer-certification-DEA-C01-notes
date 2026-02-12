# NAT Gateway

Allows private subnet instances to access internet while remaining unreachable from internet.

## Purpose
- Outbound internet access for private instances
- Software updates, API calls, external services
- No inbound connections allowed

## Key Features
- Managed service (AWS handles scaling, patching)
- Deployed in public subnet
- Requires Elastic IP
- Highly available within single AZ
- 45 Gbps bandwidth



## High Availability
- Deploy one NAT Gateway per AZ
- Each private subnet routes to NAT Gateway in same AZ

## NAT Gateway vs NAT Instance

| Feature | NAT Gateway | NAT Instance |
|---------|-------------|--------------|
| Management | Fully managed | Self-managed EC2 |
| Availability | HA within AZ | Manual HA setup |
| Bandwidth | Up to 45 Gbps | Instance dependent |
| Cost | Per hour + data | EC2 + data |
| Maintenance | None | Patching required |

## Pricing
- Hourly charge per NAT Gateway
- Data processing charge per GB

## Use Case
Standard choice for private subnet internet access. Use NAT Instance only for cost savings with low traffic or custom requirements.