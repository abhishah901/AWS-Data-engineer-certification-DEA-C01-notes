# Egress-Only Internet Gateway

Allows IPv6 traffic from VPC to internet, blocks inbound traffic.

## Purpose
- Outbound IPv6 connectivity for private instances
- IPv6 equivalent of NAT Gateway
- Stateful (allows return traffic for outbound connections)

## Key Differences from NAT Gateway

| Feature | Egress-Only IGW | NAT Gateway |
|---------|-----------------|-------------|
| Protocol | IPv6 only | IPv4 only |
| Cost | Free | Hourly + data charges |
| Inbound | Blocked | Blocked |
| Outbound | Allowed | Allowed |


## When to Use
- VPC uses IPv6
- Private subnets need outbound IPv6 access
- Want to avoid NAT Gateway costs for IPv6 traffic

## Note
For IPv4, use NAT Gateway. For IPv6, use Egress-Only IGW. Both provide outbound-only internet access.