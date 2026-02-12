# Network Load Balancer (NLB)

Layer 4 (TCP/UDP) load balancer for ultra-high performance.

## Key Features
- Millions of requests per second
- Ultra-low latency (<100 microseconds)
- Static IP per AZ (Elastic IP support)
- Preserves source IP
- Handles volatile workloads
- TLS termination

## Protocol Support
- TCP, UDP, TLS
- Layer 4 only (no HTTP/HTTPS routing)

## Use Cases
- Extreme performance requirements
- Non-HTTP protocols (gaming, IoT, streaming)
- Static IP needed (whitelisting)
- PrivateLink

## Target Types
- EC2 instances
- IP addresses (on-prem, containers)
- ALB (chain NLB → ALB)
- Lambda (via ALB)

## Health Checks
- TCP, HTTP, HTTPS
- Less granular than ALB

## vs ALB

| Feature | NLB | ALB |
|---------|-----|-----|
| Layer | 4 (TCP/UDP) | 7 (HTTP/HTTPS) |
| Performance | Millions RPS | Thousands RPS |
| Latency | <100μs | Higher |
| Static IP | Yes | No |
| Path routing | No | Yes |
| Cost | Lower | Higher |

**Choose NLB for:** Performance, TCP/UDP, static IP
**Choose ALB for:** HTTP routing, microservices