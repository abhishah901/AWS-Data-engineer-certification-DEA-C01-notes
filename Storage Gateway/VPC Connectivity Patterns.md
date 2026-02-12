# VPC Connectivity Patterns

## Three Options

**VPC Peering**
- Direct 1-to-1 connection
- Non-transitive (no A→B→C)
- Scales poorly: n VPCs = n*(n-1)/2 connections
- Use: 2 VPCs, simple need

**Transit Gateway**
- Hub-and-spoke model
- Transitive routing (A→Hub→B→C works)
- Scales well: n VPCs = n attachments
- Use: 3+ VPCs, growth expected, central management

**PrivateLink**
- Service-level sharing (not full VPC)
- One-way: consumer → provider
- Works with overlapping IPs
- Use: Expose specific service only

## Decision Logic

**2 VPCs** → Peering
**3+ VPCs or future growth** → Transit Gateway
**Share one service** → PrivateLink
**Overlapping IPs** → Fix first (except PrivateLink)

## Key Rules

**Overlapping CIDRs:**
- Block peering and Transit Gateway
- Must renumber IPs first
- PrivateLink works regardless

**Transitive Routing:**
- Peering: No
- Transit Gateway: Yes

**Scaling:**
- Peering: n² problem
- Transit Gateway: Linear
- PrivateLink: Per-service

## Exam Signals

"Multiple VPCs, scalable, long-term" → Transit Gateway
"Two VPCs, simple" → Peering
"Expose service" → PrivateLink
"Overlapping IPs" → Must fix (or use PrivateLink)
"Future growth" → Transit Gateway

## Common Traps

Peering scales fine → False (n² connections)
PrivateLink connects VPCs → False (services only)
Can peer with overlapping IPs → False (must fix)